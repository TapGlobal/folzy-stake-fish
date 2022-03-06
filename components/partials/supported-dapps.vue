<template>
  <div class="px-6 py-14" style="background: white">
    <div class="text-black text-center mx-auto max-w-custom-class">
      <h2 class="text-black font-semibold mb-6 text-2xl">
        Supported DApps on WalletLink
      </h2>
      <ul class="mt-7 grid grid-cols-2 md:grid-cols-5 gap-7">
        <li
          class="flex items-center justify-center font-medium"
          v-for="dapp in dapps"
          :key="dapp.name"
        >
          <a :href="dapp.link" target="_blank">
            <div class="ftjieye">
              <img :src="dapp.src" alt="" />
            </div>
            {{ dapp.name }}
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dapps: [
        {
          name: "Compound",
          src: "https://walletlink.org/static/media/compound.4b04f06e.svg",
          link: "https://compound.finance",
        },
        {
          name: "dYdX",
          src: "https://walletlink.org/static/media/dydx.a4830b98.svg",
          link: "https://dydx.exchange/",
        },
        {
          name: "Maker",
          src: "https://walletlink.org/static/media/maker.8ec54fca.svg",
          link: "https://cdp.makerdao.com/",
        },
        {
          name: "IDEX",
          src: "https://walletlink.org/static/media/idex.d42efe76.svg",
          link: "https://idex.market/",
        },
        {
          name: "Uniswap",
          src: "https://walletlink.org/static/media/uniswap.ba6f75a3.svg",
          link: "https://uniswap.io/",
        },
        {
          name: "0x",
          src: "https://walletlink.org/static/media/0x.597e4d5a.svg",
          link: "https://0x.org/zrx/staking",
        },
        {
          name: "PoolTogether",
          src: "https://walletlink.org/static/media/pooltogether.93a9906b.svg",
          link: "https://www.pooltogether.com/",
        },
        {
          name: "Airswap",
          src: "https://walletlink.org/static/media/airswap.8e14a79d.svg",
          link: "https://www.airswap.io/",
        },
        {
          name: "DDEX",
          src: "https://walletlink.org/static/media/ddex.a94b81ca.svg",
          link: "https://ddex.io/",
        },
        {
          name: "Nuo",
          src: "https://walletlink.org/static/media/nuo.a777d733.svg",
          link: "https://www.nuo.network/",
        },
        {
          name: "Kyber",
          src: "https://walletlink.org/static/media/kyber.7212d0fb.svg",
          link: "https://kyber.network/",
        },
        {
          name: "1inch",
          src: "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAJAAAAC0CAMAAABMpVWqAAAC91BMVEUAAAAIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1EIN1Hl7O+ep6zmHD8nfa1WpMv////wq6vd7fUKOVMPPFXh6Ovk6+7q7/Lu8vT4+vv8/f0wVmsTP1fz9vgNQFwVQVpVo8rT29+apKpTocijrLEYRFze5umgqa6WoafZ4eVQnsbHz9NriZkjTGPY3+O/x8tGZXccRl4LO1a1vcKmrrPw9PbL1Ng/YHOQnaQfSWDDy8/c5OfV3uKpsrZlfYoqUmgRRWLO1tq5wsZQbX3gHD81Wm4qgK9/j5lbdYRHmMJPm8Gut7w0ibZHaXtMnMWdsrw5XnI4MU24x846jblFjbE+Y3gnT2X1+PlDlL+stLlBh6o8gKNvhJBgeYYfWXgTSmgoM0/O2d6rvcYwhbN6jJYvbI1Ml7xKkreIl59XcoFKbYDoOVUPNU/nLkzVHkDF0tnwqao4ep12iZRlg5NrgY1Wd4kaVHNeYnIYTmuxur4+kbwtg7Hwo6Xvmp5zj56Dk5yjtsCLmaE0dpdzh5Kig4wjXn3qWGw2TmMsSlsbQFfNIkO/ztaywsoic58fbJY/UmZhqs5ae41QcoV5KUhtsdPkpaYycpMraIgYXYPsdYJraHcYUG7pRl8bNE9iLErnJUW7IkPEIEHsqamDnKkleafcoaMoZINQW21sKknP5fGXrbmLoq57lKLukZdgfo8cZIyDdIHsbHzqT2ZIL0uFKUiOJkbX6fONeYRWL0x+utiHn6zMmZ3uiJCZfYjrY3TB2+iZyN+uyNaqiJB4b32xIkOSp7LBk5mxi5PtgIohRFv/zlWbJUWnI0TF4O611uekzuSMwtyNpLDVnqC8kZfqeoYmYICCmaXN4Op6nK71yFXmvlRXZ1JVeY2ZW225o1RvdVK+fIZNZnSBXW/CXG+1UGY2R16JhlN+f1OVYIwAAAAAH3RSTlMA1vnLBfNb/eypCeJ9Ty8XnR9wsA+3hiZmRo3BlT45wLrLdwAAIDdJREFUeNrMl2dMU1EYhltKRUS0TtzvvTf2eKtGady49zbuWKOJMVriiLsaN1SrRqtJXbG2VE1wGyriCuLCMFRUxIG44h4//KGJcfzynNtbemlR0dTx/CktTfrk+97vO+eqfkJjnVqrVTeIU/0PRMbqYuAjSlMvUvWPqVIzBgEiaqr+FU2qSi+xks5je8HDQqcB2vqqf0RkA9RiL40AiPY3hFIsIkryqV6tfmxs/SZxVVR/j8g6QDRtF31B1mvCeGMA6kY2qVqnMmSi1NH1qqv+DjpIQrUAsYAQ281skvmYfVQZQUREV1P9BWIBD21ZTUAsJiTNmm4jWfBhSEnNsnvt9iy3Bz50tVV/msgYeJyoU10LFBFHumB1kGIp2l5noY2Ukum0G0FR11D9YeoBzjdoWBewE0eSINwkthQY7B8fpd1yufJcrlu5jzaTQ8U5Xq83BZSYP22kQYrtAdQxMGbaqE8SIU5k7BIUmK6YRQTQBAYufKMXmJcaQA4pRARwj7jor6eRQkuJUmfVgWNub0Hxw+Kie6mQaFTqA3XdMGWqdqPIQMcKSSYA8fUjgeI4dG2VsjqXUwteEz+FvrQ3KRUCKodpezaKlo10MNrIKRFIdVgF1rEPJoXPiU9vSBmcBtY0lY9qoESExygOdarIEXKTNPIYuHeLGeRlK31yDxFbdporPclqtSbl5W5mK9MIIFYlURdGN6ANT8rroKFkVBlZDitJBZzHmcKtpIDO8ZuOt3nHBQV5VOmBB4iRqtI4Au7X9F2dcK1DTW0pBva3wmYv8FlgWJX1UdrIjo98RtA0qForCiggTgDhaZoa0FRXVadCLiHXCewSKkQuIa/dkEk9RVhxG4ZFqCYAdfU4IItu58wKCwm3CDmV8xgU0XuIEPIQQFxYJl+LtlDXB1JpbNJScUKoIHkOqvSmqMCZSYjDQWweIDwXuQZYNwxawGOl2SjCEyEE08lyjZKyiUy2lf5pD1es46L6jR0G+JqV9PWsEMwJc74QCvu2azOhbHaxk4/kAJXLHtdVf9OoFu73ZkZXpN8J+vFVV8zAMSGUL5dNbBrT06UF8ZaQIgDKA6RKLVT6PaH66NWKGeX7DEwKm8tmSKwKFbIWWZ4EvppGpMFX7MZqGiAm8ncn/7x+D4CnQhlOXksGkABKeSG69dBzLOPJLiljTz8U5NgVY1Yllm0n/G6J6mHGoLk72iK5TKAPUB1x5Y0ZiEf5o5edaReB5GPJCBDTMFqnq6WJACUl63dTXqUytvXhtxoBhdE1QNy3OrGfOHFu+RVid8rXOakGAKInxe1OMaAMjwuLEFHl95pWF/GtZnW5KAVb5iwwOpHb09a4lh8HmMqfe2nIDmUeIhKnHhRkGSEj2jPJA1CitDGa6LqVqv2SWY0oLGo5PL6vEbgsSDwFpnfjVicYt/J8PJJLhHKx3iRBnHpTYE91u7Ny2OWpEAq0dWr+wiKPxvjO+8fxE6jRAYFhRvxwrsVUwwSe7yoCyJfnLLhU6WmbbYQ4sh/l0lv35iC7BwhCU7OiF8vGwJ7WvXnJiG3GEhh2c9x5zOV5fgUwGrD4YrTL/KOjJe+mjfihdk6EoG1UwTJpMESv78Pz+wFkCCYz1nEcN70v9RlqxAx+lAiLr0bJuPaj49fqSst2UJu3SS5CvMC73XcXTbnRc+Uw+InSVejBtxKQqG/do31CXwM1OgtxIcc1T+jKD+wwGljM8ztE5Mu9RPIBU4XuJ6ceA3ebydw+/z7BX6WaFQh4bWCyXj9zf68Oiw2grKQFWriCH9lnCP0HTxklT2A+KMeu/FTpuIMUAG2vNgtwddtKUc5SXEUqhN2J63t25fl5ANZfoELth/ILLwLjO/A9enThh+CYSRKKjwdgLglpVl5eevqJkpOy6ltSaASW3Hnx/JzCafU+n5I2tsyQl3Mbb8iqomcxYiG+2Hw1FerGT2pvxNQOnQZz3IhONEtXJKHpzW8kAKFRsrIpe3AvxZJ/oMSUS5weoP/SppS91+/cLlW6ewYSyptAVcUb5YMMxur1rSZtN7J+MTrzg29g/Mgezdmb3p3GwSxlaDpV3WIsN0rpN9mwez3weN0AxDlN/ex9+Vw2erZsjPIxk6HWhAjpwFhPS7SoLRLGcj4mtbjYbyEnM3i5dOgf8+muHicC/kfbVYrl/YhtRyfTwYJpTZXsveML1Lm9O8HQKaoRPHjVI4D4ycCN09OBfomcTDcusSdXyiYjSoSTgO+j3kOHAMiQinSCvgTdI4tTgI1Sw0KVzh08DEYD/8Nq6K2gLoDERDDESyM4Bbu5Uui18qmQASxib1gPF/cCzFKSLPmmoMs2OWQH2tASBSm98NVojghKPf/RDl3IaY/9+kGGhGHjt6zmvkc3A05eBo2QzIguHcYBFmZ0Fhly5xRHXA7Qf87s2dOWdVcqHXzGllJTySiiiX/A1cH3IaC9fhG2cT9iC2ABeo0NlIzuS4O0wZ9IlzvFbTzNZyTTZsOS2e1KlViR7jRdA0pMbemQQHCINFKeeyY0L9+kOXPoth4Uwz5lQ/tIh5/ZxJJlMQkZl4OMvAjQ5swyv9F1mqSDTY/IwW4CRpm9FAd2bugnX+K+w6zBrEPbXr1a1I1T0mIkzy8WcUAwJbM9fiVZMW4s2rYsKJnvVzp4jjat3VFIT9+1QtYSO+rFVnp9/JTvCQ3gqVF5tOd5fiKSdwkWwCKUIEMxbDaWbDeUiEs6lhpdb7q0PwtPtSgwossMPWD4RqeZB0VZxnF8JC3Lmspquvu+z/Du9O4uC7uwuLCwKKtcCityJAmIF1BimhQoJZgTBXSoZSEdZDZG923HZGZOU5OW021O4+Q0lTNd6kxN/9Qf/Z7j3X3fB/zMYMPQ4Jff7/u7HqQO1NFt2AQCRsGK4rH9Kj8LGes+nVTGErSwdFkW3qTE7dCS9u4oXLzaohR9+o1piuKfCkJ39TSgwONpTcrJDPg/KMXKdX4jKahwwWlDNERnW5s3iGfvhDNEux8UinbBRf3tykfkorx6JEmbrPXphz2eQUOSnZVRtBFYxOVISeVVVayiemJ7MRahdtBV2ow2EuR00WuUNP4g8QSc5ChF3/5smjcjxaXaG9Ggx7MiqWdGEKOnQJ/7ZsgREqlkbLXPaWf7k/mM79wHEezFpjcRkgvwm7JNPqbW7O+O3HffK4/YoapXWfvJNHNvhUR/W7r4LMQ9Hp/MlydQTXpOnvQuM/zlsqoqWN0AY+WGg/lzCmR3JEElaEMzi2IvSqwucdGpa+oxESPFrmSxKRs9Z8pmhEdF19YbUbfHYxAZWZnGIJ44eezYqZCvvEZNfVYSZIzNMhwszBef+oUgWFV8X8JIXJyUbW2OuaZ43gubu9UYMc28HABlG7S6J64APqDVg/6CVZ6MnbD+Onbs2N9gbFjOeb60DZOxZzuTVs42F4joUcrQx8sf0Uglz9kO4K3UVfLlg8LdXzlslJwloju+aJZBn2Zn8llGigIBT5Z/Ef4jPSdGvZHetdLTMTaCTgpFjd/Zv1ezfLJYDYt5wY+BHqCWVNHmfYBfLg5+5QH6ASleMG1uBMpaTG6li/SXz1aPJHsFRk+c+OvvJ9DAHhfDzVcY6+lBJSPmGJK5IpMUnPkUoZGSJkZUoZKRcDJRF8S2q9j9MTe2q2fn5Jk29dhumvdCf5+czoeZJCOIf095Ea4cYZ2jwuezaKvtQQfjqKQFssUCUsjYQvpQtEYY6wVo0hIH7X3tywd4N3oPLlKb5J77aeo+Oq4zXkUe4inLzMxeB4Qqa8kxVf9sWmcPrMohlDLOEkOSmS3HvU4MuLMLwQRsW/Pw3HUkBDf3mjZrNignTdNX/H4S5Nu2f38daiOsaqRhdNMo6ZEBYnUNSpA91DI82bIL6XjxBtDTDKq2VOk/ryuylK0Vt0F/DZyCEE3XLKN60IuNs2cvWdtc+3u7X3o3n3pxtEOkzOHrbM9cOcs0wgBZvIp0Jbe1lx8gSZ89PnHOyE1yqE3Rbo6NPGPcqf3aUkRzjDV5IU3taEZZngC30UPMTVTccazSHiK7d9/xGp1HFCQLNqLUJTctN4ntANI0Tx8nQSIL1e5NYx4jmgEqe3eI5pL/6T/rOjVB3j5GNAEH1EBTvxbVpr4pWJyeO6Ggs4EZJCjA9dQUGApVSESdaMWK6+wQUYqJYreiWvX/JdClNn4arxZ0ykzO8vT15oSCpiIhKp53u4WGopp/VDCiF0CCEa5CC8gc+4JDbAL6krb+mm4iL3RauJ7G9BvMiTx0jRj2YpZ9zuwltYBmaRHpIUpArGU2RXaIZJLbvT1sPL2gISKh0/GoBY0beb7S02+ikU+CtCo7F1gnPf3OwJKkmVcb1+UzzoAFIs5s5tghUlkuDg+z8ahWpDa1jwC9Nd6UTswkXeP70Bmw+DdfZbR3JIuom21eyARDXsAVohojFaIsntd4R4SNY5l6bX9LrNdvq6p3TPylpGcr1T1lbY+7U18ILBNTrKCulhXYZymTRJYBqCvmfzAbe3eUPwV/+Wtg41gr3+Gv3yvb9VG42W7eQIJIzBb6uMU9y6YD33uIwLZQZLU6AW09TQmercO5OQCSLWdWMkQyaf5Wq4npVEkT/fiJSpoWoheEoMVmbiMJetV9dlzJV3ziOm+J9EdRsv82WwA6Dj8tmnsJU1Ah2r1IJm0nd5hOGIf483ubWma/0gVtSU9vzCUnbaGR73qduVCuHvPa78EAH1W+OUyiyiv4E612LRYQsp1CYVRkqXa6DJ1Mp467egcOqfe95y1dEM9Y7lYqtDzLtTGey9t09jMgYmyGMbsiMtDX19kU4b4knvmDdl+RZtIrKfQbimzVvnYiHGMai3hr3Itn7R1tl+YhErScAkR/bHD9mub8abB8njFEowgztmBBYXOirjXOd5BmAKHjdGJy1jhzlmrmHuXrVvCJkV/BUlTSubZjk5ogbxylQ99V9uSh9TxA6XnyGrrGPjgm8e21H+/4jXkfkl/za3tErcsAJw5f+4uaymVAlClmG3qI9iHME9pd4RZ0CHQciTsk9IXbRGtI0GIeoEZ1wV6cuhGfWeUZpJNHXBfM9kkDCOvwtT87tnH0UhBouFFibTJUiHylGOL1V5TPbILo+hHE67wdHcAud+FvMJduFQFaKhfGacnftyJOtVK34h7v93Pm1/DCKo3y6VRlARijRwrJdkBN/M1KkCJTzZxi0aeW8AamiKLtdXDaaL8+CBzRZlkjBUi2onrHjn+F6EGZ1k7bsUMA+nppZMcBPPk+FRghsyx3ovlKkKM58l2tHeBz3mfMUEv2MDjNcQCHxCHiuqhzzLylZl6jmGYtzrNskuhBgY4VQbUTh63fS9AgigTBT59Tx0oZBAk+ycrVeFVkyV7kj6NT7ibdatzLn2AAxF6qNjf3m4tnkovENFujLml1Q0epk/hWruhTnRDbPCuDCZpbrUCxMnRLDhQxStkCHgdCs/WHWCR6ptrpIlFelhH+gxEHDsHNo7S7zuR6GuVGfdbFyXusjjf/wXUjTFDqNfq9/ftKxTf6UxXY/bBp4qN1SYXhIEPlbB9C9uCdpX6nJVzQa4HYBL1RmzRdpYX4tz8jNcbivNM+3F+lJuLYqmXtngVoYqXceILfkKSWysyYV244yZSbyzxgmJtIvT3WDg0761VnjckdLS3EFV+R6tIWn92+IrvdP9lOza4fI8NAfarAFMJchp9v3ZqtyURhjNh+9292nmpRjGemdLRqi8pC55zJXxdxXL2EEQPyoJ4dDMdqKc/S0BYUqswMHWWiRehMbgK+GpZiCOO4VSSMWC+70JTJfKieMV1M+ni1SjuLJbCTLP5OKNzEgsB2Yeh6OAhOJChTLiEb0ZBaJ2WDVAShs4cmmWCLmZujdo+rp045hy6yNGBMnssssogO/LnHE2itYk187ZVD1Umce0gnIF09JgRxf+lX9rAXGjcvT5csN9eoV+rL0nCR/Yi/bcYSvot1INi9P4o4FcdwKZCTqxmIKBW7h44UVIxmW5A0dopOuLEWN0o9W2XJTJ08+QIA021fozLW1NwBeFdaSAxxL4VFWE1zQxlchMXfqJMpBO3HWufy5l/t3I20trg1XWVMvqFddf6VjnfP6Wc5UsLlxErs19K8W+HGS6ODWo8maK4Q9LkVY+LLiqLC0ybtpXTFTFljl02D8+64fCokoVrupM4wiHtbxIh3YXFBC0iAJihDmHofdWrxZZtZzoMWTp5SetZLj6alAa5HvfMvknpoi+/ti4rw3J2rVTyxciNCrIKnyNDI4mX/MG/MFX4jxWbXupainrSorng7UpznfNKbJCWFZCT28PDoCSt78h5ERVlnGRqrPOqBmL7soNqRtFhifMYa88QcU6RR0aeYfOYkKLxjufYzkotimp/xwgKeoXGFn6kE0Zdt9Pesh7zjMnaDtLTikvH/npGT+L+Za/mJ6grjrfKs1GqV1tLaM6Qu5gUOMjO8mQEE5CGIDzC0BYZHKojSFMJLqZuGIkQlQVrDCjCRNNWkSwhJpdFdF26aLty2K20X/Q/6nfN999x7z7l0JhVbf5uakjA/vvdrTsUvvyGfq3aFBVvAsQNcAvUaIT/Phw2qgCi8STPSNNaDg3PCIf1ABqQzBvcHWJThOsvEAo8017zCy10aIww8p611iTaErFY0No6JHqEvpsXeakZsHzmIvEReCye0LnxKM2oy4aJyh/9poiCAFrpBhDowSoNHM9FKK+CelvcH7PmVooww4/IDoRVRkYGCdHhL66osyiJuVbYRbaX4eOIzj/NpWBRvMgzT+mnDAggI2zAtBDXUH3PNiKWsCDo6ws02fUXDckSpmNFd6fP9gt8VYdmpbzlYUBAE5GDReCxzdNB1bwZLVlccoD23Yry2EuISGjEEFAIBQcAj48jUzk9RQEZZP8zs6M2BSn72K25BaEJx0VCKjE7YJjSmgDpAQLWTkSNk2Snq7QcJ6He5E7Gh2AsJVFw55DpqzHnX2KBY0UXyeXKxzclO+VlpSfrtB6vgNxBISHF59shF47sc3vMkhjCN/buIDnZEj0lhEZyZR0KojHccbj88cONDfc8QUzBWj5W8/yhP7AniBDJqcBDQLUoGkQ4cfaTu128/2F8goCOIGwqfoJc65tyEBUT2DIx8RWRBUkAxY9PREQthT5Ou3XsBft1eQGugMUA9eFjCAiKXb5WeX0kCivUQndAFSB5X3DSLUVeubEDGRM2C2JZfEMKuOUFQtgdfC2MMQgFdADoknnkoGFFAmU5B8aGMif1MxVdgQgR7tVjS2nzi+Wzfgr7Tl3V1aRh0Rt3ZyC25SuyJgaeFMN5pAsri5fvPUkDDTEGNb5Do0H4GP98b7cqeavR4Kloxv+rwcipFVW1G/zpk0uHlUAQ/SxNQUhr6PAoItaqEaWHT6Gi+6GmR1EuOl2aXdbvZ7ChnMzjoIugFUV0zFdXDNCu4NI65g6w1da/23RfAshTQfaZiQcxc0IDKL+O2PFoEjVMNq1nEipGCpS4iwQhnIO6r3NEvxWR5RpcN+5wKoT4pIEh1KnpdxMcP54yi0ym5yc3Uzdq5eHKOwg8kBa8uInL5B7HY+MfEhhsQdX1palp9I5nB5EUKaJppWPYTHxzYlcNSDbd6feWYba3yafPZRFQn5w35G5IMGdCVWqo79CDk/oViEK9RVLi9fuJTwn/9afgPdqMXWzC5HbN5Vpsuomp0eSs6DO/ZneSksQEZpK8wDZWuHOSDmfuErytbXA+7P6NJg5LCwqoVTTAqO0zcMgaXu9CiVR/7EwtXXO6pGBCE/MbMpi2KR9asgvjYHcybXeCzi6ishteFq1Y+MVmTZui35iLyQWWPGGEKutkaJ1Qv83ZbEU5YglU4YFQr2rqpez5baVtNlb2J+UJFYWqiD8j5+FWmoG+ZzQChQbP4qyOvqeDFiJ1QlU/QDvxkJfhcUxgYNHoYfYtQz2MVcBDm2ByCnXg9C1B1KG1fJZeqi8JTrqWuFlXHdY/lXHTZoymsAyfNep1Ig2HGFqmS1guPRzCqW3f5/fZ6/RMuOlCYmt9KSk9xQmXuWTPBnkUPUww6cs68YNbDtOdHCoowVLcjDzxmZot+9WVby7dFAkIHpGxWely44lm46CfMirMBCx2xGQ8pBqSYUB/5vB4VF+BX9j4V1ZZFPgFOtZwsCM0ox5/DD2aKinzc9Kuho0RsMTUkxkKGZaSRAemn7xXk8zgRteBsObfUhzBIMHuHiXaiKjVmqQTqIAjV8aDZjXw+81CjITFeKCPQYSc+Sck8V31n3jtZMYAhbjQsG+KyM5UUDEowBllRDxLKbj4lBsFBnzDySvR4xcHQoA85fx1QFK9HnMJ0cB3DSWuXFE6jx/KjHDIhS+3mo7B5h7EGHoIGNI/v4Z+Sj32GfM7jPSWRFWMaI1ESPBUtogFtMEz59vligyn8yH9MoQOmLXqwm6cxTPEpwCPNgDrk5DudvheXnsyyVJseMKJ04TMmPzOMdE6THZ+vkXb1BMw5V2WDbVvU7OF7eURUI9Al7vAisrz/Bt8kABv4Z5KaWSdJX5NGJXRxvVzQiYraoeDr6mJJ9NGKLhyzuL1p7lseunrdagS6IPm8fvBgygEcde5Rb81phXB1yW0kr15hO95mTufkmT6P1OJab4mrPtfUUa7l3zkyt2Cm613xqAYd43xER5OckYls9GyfjKV35D7RKa7AqO89XsQ11e6WIXLt4SlXzqBBBQIP3Q/mAgZzbHOFAuCyVaxGxPEQ8TGhJ4/9uCC+Su7e/rQEU4Cgc7Jdamq29xSqCqk4I2qdcuQJB9uwZ/jOG0zBO04ta4RWqgNjLqJTKn5tHgnt3iLQrB8cVKlURZXCR93+nNuwByCdzwGnxFGLceFsr6RjLnGZZ3bRS3lK6RDbwMS6Wkx2N81YzhD5qxY+PeA1trCLtu00WMznvN0LXrKdUtoGCzoLLQ6zsapomxz3Xj7eEA6PRo8rmxbN4TvAbfINosPfLjH95RByMkRwDOk0Fxl/pbjTWYYO8KilZD4VjrZdRsbb4wvic9cegDqH54aXNienh64YS69kcDAVexhiUcYdRAGPg5WjLhoLwVC1tbntMrCNj9seJz42TLNtX8FIpiyK9Y79r4Smoh4jsK8LpJIgTmJId1v5XAjZ+Hzulg6vgcLTFq0BZNrKEzUztmPYbSTKp0mXD5k1YH4euBEf6g+dJTRmGU4WXL+If2MY64tcnKokhqma7fjIUd60Mx9CmkYIruAQfSAgylFdnOen7Rcrz7ZXf/r1ye353Mn7Rz4fd2DfJwOiDtpJrYsGjw6ZZHmfY1TwdVRGE4KB83f0w0Vajcr4o2M8QrWr5KMjk/IpjW/5vb+Be0AIBeRzWOPWnFEogQiD2/Mh0y5cYoq+VGRR9zVKoX+KSTR58diVZNfHFATP412j9AM1X+jq6vwB/V36l44UuevBg68y2wbxGI44SzBy66hp/PTO7W+mJs5U15iH0s58YpBa+yFUx3sXaD9DeBqovGpiJhZxuYsSmmIJYXg78UB4dmP+elenobsZu0brv2qrAFrqsW8vxTl8fLgfbyueThql7ovzutT79Jt4DeyrU/bra66jom8/jXVyXDib8zwXz1A+ms+huA80MYGfFgeqRMU3pS6l/EYlWBBkcTCimw+tNSKbVG7sTeCBDYGnLm+Dy8tV42EWNJUP1svS68s46nrgqK0IT15YCKVmaerSsdeS7aO6qVT4cSOPB3z/qC6n6Dwu+sJhEo9snROw6s9w4wZot//Zy/VcZ3VUAmyPuQ0HOtx4CidrExcPNWaABtnEVCtDfFzJ0/F5QCg0WAMFbyCoi0enE5qmsnW3Yj3xQmO5tJRuZseK7YjjZCVr/CS7LMACVDpL8eh0AEM0sUwD50oUB3dxzfjIl/Qjv277sntiQphTDbstm4tzmnhoJTZETUbqB4m/30h1ftDcjd5mNpB5lRRlnyiyfQOgmvYFtZpzzYsdVOhzosMy42pLn+k1yb5TMyI2S01gVwsyqjve0NpcFyym61KFDy3oIt+S7cDjWP/iGUZWSY0eqcMGTwu2yaW+ckh2N1t9oh+4xnV2Xp3+xC4VijnB/VqDjmNijx+si3GEKtsGG7boVDJsXfXMsDN0obwq7RjZRKZvMEkn6V8+DMmWUURkIMqlF/VkUZcFj8SNYIB0JjfNoaGlWkbY/WbCFPQjgll5waonCXcrcrA18tcEoevcyTAkCzabcteWeuDwiz12ukjfXHUKyRUuHZXsOs1d2Crm8/5nkg1Ly9r/Qu+ggYiKRwUjdP121mgz62WNzyg/rabbu8eXQlDubDIpnEwwnRdDBrcUr2B0QiwOAsKB8g1zqHmyMvb0p5m1FUmolx9P0znHMM8Q+eaTRzvwim3S+6ZimkuhGYbsIMaDdx/MWddVwRXTyViZSG95/N6//4bBJuPdHXpqdA+FZEAU0hUWapgSrIw8z8nvB/A7CqgzWoomZ+zgu6x7dxnxZqyJNZWhLjDCbBAj1F8AJ6LQFE0oJ6UHgM4OIgt1Fr4HFvMNOpr7I8Lq4weP765+9IDm1OujYiR+Hpt5IwYmHHQSz2jVLt+TIGPtwji6eYBRcNew3L6FdcbyTpq5OA3egNphvAUmW3INxPKlnFvOfaRiY9gawysbqxtFxZa8M4/U6mOHbuBjfDPSw51Mx6o2Z6Zbkp1HlvG9DVkV9d+iywjCx+OxWz2hfpj4K0jfcTJyW37W8j3eEVrIRCI9gEhhiDYi08rpQ9o7L+k9bx6Krlvu1/KfTfcXHrGic+j7JcuoOTU57fXMjMM7aM76DB0czObM7nNzS/cnAfeX5kZq7TPvFw+D8R8cdBuEupkGhc1/8cZ5uhHs+HsC2yPtwKGXJRv9HNaDCaqPX+y/nb6HKUjeve/QSxWNXlwHMD9RbDn4YUpG1r50wL6sjJTDIJj/FgdBJN2QxnigOfzaq4AP+fNsAdxjvRpISWWMrmheEaTsEiHvzddeGfD3d5NTXnuVkAGDwP8NfwPD30yH6Fx20AAAAABJRU5ErkJggg==",
          link: "https://1inch.exchange/",
        },
        {
          name: "Sablier",
          src: "https://walletlink.org/static/media/sablier.6d6361a8.svg",
          link: "https://sablier.finance/",
        },
        {
          name: "Zerion",
          src: "https://walletlink.org/static/media/zerion.4fc85d07.svg",
          link: "https://zerion.io/",
        },
        {
          name: "DeFi Saver",
          src: "https://walletlink.org/static/media/defi-saver.de4f3a4b.svg",
          link: "https://defisaver.com/",
        },
        {
          name: "Synthetix",
          src: "https://walletlink.org/static/media/synthetix.3ced3e5c.svg",
          link: "https://www.synthetix.io/",
        },
        {
          name: "Set Protocol",
          src: "https://walletlink.org/static/media/set.afbb998e.svg",
          link: "https://www.tokensets.com/",
        },
        {
          name: "Aave",
          src: "https://walletlink.org/static/media/aave.61fbbbc5.svg",
          link: "https://aave.com/",
        },
      ],
    };
  },
};
</script>

<style scoped>
.ftjieye {
  align-items: center;
  border-radius: 60px;
  box-shadow: 0px 16px 24px rgb(0 0 0 / 6%), 0px 0px 8px rgb(0 0 0 / 4%);
  display: flex;
  height: 120px;
  justify-content: center;
  margin-bottom: 24px;
  width: 120px;
}

.ftjieye img {
  max-height: 80px;
  max-width: 80px;
}
</style>
