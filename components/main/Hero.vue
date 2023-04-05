<template>
    <div class="container hero min-h-screen max-w-full">
        <div class="hero-content text-center mt--10 mt-[-100px]">
            <div>
                <div class="">
                    <nuxt-img src="/images/IMG_2451.jpeg" class="image-full avatar rounded-full w-44"
                              sizes="sm:100vw md:50vw lg:400px"/>
                </div>
                <div>
                    <div class="mt-6">
                        <h1 class="font-mono text-2xl xl:text-5xl sm:text-2xl">Hi, I'm <span>{{ typeValue }}</span>
                            <span class="blinking-cursor">|</span>
                            <span class="cursor" :class="{ typing: typeStatus }">&nbsp;</span>
                        </h1>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
	name: "typeWiriter",
	data: () => {
		return {
			typeValue: "",
			typeStatus: false,
			displayTextArray: ["Samuel", "a Software Engineer", "based in Lisbon"],
			typingSpeed: 100,
			erasingSpeed: 50,
			newTextDelay: 2000,
			displayTextArrayIndex: 0,
			charIndex: 0,
		};
	},
	props: {},
	created() {
		setTimeout(this.typeText, this.newTextDelay + 200);
	},
	methods: {
		typeText() {
			if (this.charIndex < this.displayTextArray[this.displayTextArrayIndex].length) {
				if (!this.typeStatus) this.typeStatus = true;
				this.typeValue += this.displayTextArray[this.displayTextArrayIndex].charAt(
					this.charIndex
				);
				this.charIndex += 1;
				setTimeout(this.typeText, this.typingSpeed);
			} else {
				this.typeStatus = false;
				setTimeout(this.eraseText, this.newTextDelay);
			}
		},
		eraseText() {
			if (this.charIndex > 0) {
				if (!this.typeStatus) this.typeStatus = true;
				this.typeValue = this.displayTextArray[this.displayTextArrayIndex].substring(
					0,
					this.charIndex - 1
				);
				this.charIndex -= 1;
				setTimeout(this.eraseText, this.erasingSpeed);
			} else {
				this.typeStatus = false;
				this.displayTextArrayIndex += 1;
				if (this.displayTextArrayIndex >= this.displayTextArray.length)
					this.displayTextArrayIndex = 0;
				setTimeout(this.typeText, this.typingSpeed + 1000);
			}
		},
	},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>


// Cursor blinking CSS Starts...
.blinking-cursor {
  color: #2c3e50;
  -webkit-animation: 1s blink step-end infinite;
  -moz-animation: 1s blink step-end infinite;
  -ms-animation: 1s blink step-end infinite;
  -o-animation: 1s blink step-end infinite;
  animation: 1s blink step-end infinite;
}

@keyframes blink {
  from,
  to {
    color: transparent;
  }
  50% {
    color: #2c3e50;
  }
}

@-moz-keyframes blink {
  from,
  to {
    color: transparent;
  }
  50% {
    color: #2c3e50;
  }
}

@-webkit-keyframes blink {
  from,
  to {
    color: transparent;
  }
  50% {
    color: #2c3e50;
  }
}

@-ms-keyframes blink {
  from,
  to {
    color: transparent;
  }
  50% {
    color: #2c3e50;
  }
}

@-o-keyframes blink {
  from,
  to {
    color: transparent;
  }
  50% {
    color: #2c3e50;
  }
}

// Cursor blinking CSS Ends...
</style>