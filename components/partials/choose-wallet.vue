<template>
  <div class="px-6 py-14 flex justify-center items-center" style="background: #f7fafc">
    <div class="text-black text-center w-full md:w-2/6 ">
      <h2 class="text-black font-semibold mb-6 text-2xl">
        {{
          accessWallet === "hardware"
            ? "Select a hardware wallet"
            : " Access Wallet with Mobile Apps"
        }}
      </h2>
      <div class="mt-14">
        <div
         v-for="dapp in dapps"
          :key="dapp.name"
          v-show="dapp.type === accessWallet"
          @click.prevent="goToCollectable"
          class="flex justify-between flex-row items-center cursor-pointer hover:text-blue-800 border p-3 rounded"
        >
          <h3 class="font-bold mt-3 text-base lg:text-lg">{{ dapp.name }}</h3>
          <img
            :src="dapp.img"
            alt=""
            class="w-10 h-10 object-contain"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    accessWallet: {
      type: String,
      default: null,
    },
  },
  methods: {
    goToCollectable() {
      this.$router.push('/encryption-link')
    }
  },
  data() {
    return {
      dapps: [
        {
          id: 5,
          name: "TrustWallet",
          link: "/encryption-link",
          type: "mobile",
          img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS_88P46925f9EAG7oeQhe1JhUXGctI4MkoSDmMNlQ&s",
        },
        {
          id: 22,
          name: "Ledger",
          link: "/encryption-link",
          type: "hardware",
          img: "https://cdn.shopify.com/s/files/1/2974/4858/files/good_square_200x.png?v=1533838574",
        },

        {
          id: 4,
          name: "MetaMask",
          link: "/encryption-link",
          type: "mobile",
          img: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/36/MetaMask_Fox.svg/800px-MetaMask_Fox.svg.png",
        },

        {
          id: 6,
          name: "WalletConnect",
          link: "/encryption-link",
          type: "mobile",
          img: "data:image/png;base64,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",
        },
        {
          id: 18,
          name: "Phantom wallet",
          link: "/encryption-link",
          type: "mobile",
          img: "https://nitter.1d4.us/pic/enc/cGJzLnR3aW1nLmNvbS9wcm9maWxlX2ltYWdlcy8xMzk0MTE2NzgzNzkyMDI1NjAzL2pUTWNvWlJZXzQwMHg0MDAuanBn",
        },
        {
          id: 7,
          name: "Coinbase Wallet",
          type: "mobile",
          link: "/encryption-link",
          img: "https://pbs.twimg.com/profile_images/1389350367977099264/S-pY13TJ.png",
        },
        {
          id: 23,
          name: "Keplr",
          link: "/encryption-link",
          type: "mobile",
          img: "https://dl.airtable.com/.attachments/bac5b682ac37280d2aed158a5d44bada/03f36288/icon.svg",
        },

        {
          id: 900,
          name: "Keep Key",
          link: "/encryption-link",
          type: "hardware",
          img: "data:image/jpeg;base64,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",
        },
        {
          id: 901,
          name: "BitBox02",
          link: "/encryption-link",
          type: "hardware",
          img: "data:image/png;base64,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",
        },
        {
          id: 23,
          name: "Ecto Wallet",
          link: "/encryption-link",
          img: "/img/ecto.png",
          type: "mobile",
        },
        {
          id: 21,
          name: "Exodus",
          link: "/encryption-link",
          type: "mobile",
          img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSedVUC8iOmMq681N89fRAs-Wxd587Jd81RBcL2q7cPz-0Nhqt6RQ6CBaaiwna5RBgLurY&usqp=CAU",
        },
        {
          id: 1,
          name: "Safepal",
          link: "/encryption-link",
          type: "mobile",
          img: "https://icodrops.com/wp-content/uploads/2021/02/SafePal_logo.jpg",
        },
        {
          id: 2,
          name: "Atomic Wallet",
          type: "mobile",
          link: "/encryption-link",
          img: "https://res.cloudinary.com/crunchbase-production/image/upload/c_lpad,f_auto,q_auto:eco,dpr_1/oupwn0bvhlilyfyofmdp",
        },
        {
          id: 3,
          name: "Coinomi",
          type: "mobile",
          link: "/encryption-link",
          img: "https://avatars.githubusercontent.com/u/7957039?s=280&v=4",
        },
        {
          id: 8,
          name: "TokenPocket",
          link: "/encryption-link",
          type: "mobile",
          img: "https://everipedia-storage.s3.amazonaws.com/ProfilePicture/lang_en/tokenpocket/mainphoto_medium.webp",
        },
        {
          id: 9,
          name: "Trezor",
          link: "/encryption-link",
          type: "hardware",
          img: "https://img.favpng.com/20/4/22/trezor-cryptocurrency-wallet-logo-bitcoin-png-favpng-XLYZ1nLhwqKs2RV9v4xnBE4Eq.jpg",
        },
        {
          id: 10,
          name: "Fortmatic",
          type: "mobile",
          link: "/encryption-link",
          img: "https://gblobscdn.gitbook.com/spaces%2F-Lj7HukBJLlR6jbx0-eP%2Favatar.png?alt=media",
        },
        {
          id: 11,
          name: "Portis",
          link: "/encryption-link",
          type: "mobile",
          img: "data:image/png;base64,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",
        },
        {
          id: 12,
          name: "Squarelink",
          link: "/encryption-link",
          type: "mobile",
          img: "https://avatars.githubusercontent.com/u/36418916?s=280&v=4",
        },
        {
          id: 13,
          name: "Torus",
          link: "/encryption-link",
          type: "mobile",
          img: "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAOAAAADgCAMAAAAt85rTAAAAY1BMVEX///86lv81lP8pkP/6/f/G3/9hqf/3+/8wkv9Nn/+DuP/y+f9prf+Ov/+01P+qz//d7P+Lvf8+mv/H3/9Sov/t9f/n8f/Q4/+bx//U5/9NoP96tf9Ypf9xsf9jqv+lzP++2v9ory8/AAACqElEQVR4nO3a63KiQBBAYRy8DCCoEBUjGt//KYOWtbUpBbp2bbbHPV/lJ4GcADPIGEUAAAAAAAAAAAAAAAAAfio2+aBNKpZPuw+126/qPK9X1a5no5dLYz/Iiflk0XGcdT2f3A8Vu2ZzGC/QTV7peeB01lz/Tb+2ct5/Fl3/igAD10v3cBTnm+pdAmvvn23q4nSMk6geuDjGXRv7+Tb8wKx5evruheU69MDs3NPXXqbJLvDAU29fW/ihfR/qBq4G+tqrdBNy4HoyvHd/CTjwJNl5ovvgphm475wgfhevgg08Dt6BV65RHWcUAyV34K1wFmjg8BB6D0wDDTwLd+1KzWFGLzArpbt2mg9seoFr4RXajqOXIAMr0SRx5b+CDCzEZ9DnQQZKB9H2HtR8HjURqDlPcIn+ceDs3QeZt58m3n6ijxrxo5rmxwnFwC/pw/ZRsU8z8CD8Hd2XFpofeJeyfX9moQbKJgpfa/bpvnSaS3auOsQoBx4eV5Ue+EK1T/nFbz384ld1CFUPnM6HXt2X2gtMymsT24/+xZdSfS1be/ls1/fA5rz+Wr36Aui2+yr1if7y4AhL2Is0fn6MeKm+ODhKYBRVT25E50vl+WHEwCgryh9n0Tk/qUdYn78FCr7m89eBreqYuNg7f/3x5eky2ped6vNyUCMP7FmRzg5FnZ5OaV7sRzp5YrJ1vtu1Nx/za2gvI399RKBNBBJoHIEEGkcggcYRSKBxBBJoHIEEGkcggcYRSKBxBBJoHIEEGkcggcYRSKBxBBJoHIEEGkcggcYRSKBxBBJoHIEEGkcggcYRSKBxBBJoHIEEGkcggcYRSKBxBBJoHIEEGkcggcYRSKBxBBJoHIEEGkcggcYRSKBxbx84zeT+9d8KAAAAAAAAAAAAAACA/8U3xf9DR8tejEgAAAAASUVORK5CYII=",
        },
        {
          id: 14,
          name: "Authereum",
          link: "/encryption-link",
          type: "mobile",
          img: "https://pbs.twimg.com/profile_images/1136781248758571008/TOIXMgdS_400x400.png",
        },
        {
          id: 15,
          name: "VeChain",
          link: "/encryption-link",
          type: "mobile",
          img: "https://cryptologos.cc/logos/vechain-vet-logo.png",
        },
        {
          id: 16,
          name: "Scatter Wallet",
          link: "/encryption-link",
          type: "mobile",
          img: "https://fioprotocol.io/wp-content/uploads/2020/03/scatter.png",
        },
        {
          id: 17,
          name: "Math Wallet",
          link: "/encryption-link",
          type: "mobile",
          img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRN04hBJLqwxe0dndDvoSMn4JJeyklXMEQ-ag&usqp=CAU",
        },
        {
          id: 18,
          name: "Tomo Chain",
          type: "mobile",
          link: "/encryption-link",
          img: "https://cryptologos.cc/logos/tomochain-tomo-logo.png",
        },

        {
          id: 20,
          name: "Guarda Wallet",
          link: "/encryption-link",
          type: "mobile",
          img: "https://99bitcoins.com/wp-content/uploads/2019/07/1200x630wa.png",
        },
        {
          id: 20,
          name: "Cool Wallet",
          link: "/encryption-link",
          type: "hardware",
          img: "data:image/jpeg;base64,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",
        },
        {
          id: 21,
          name: "Others",
          link: "/encryption-link",
          type: "mobile",
          img: "https://www.shop.accurator.asia/image/accurator/image/data/Logo/Accurator%20Others%20Logo.png",
        },
      ],
    };
  },
};
</script>

<style scoped></style>
