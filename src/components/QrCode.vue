<script setup>
import { ref } from 'vue';
import QRCode from 'qrcode';

const ssid = ref('');
const password = ref('');
const qrCode = ref('');

const viewMode = ref('form');
const generatedSSID = ref('');

async function generate() {
  if (!ssid.value || !password.value) {
    qrCode.value = '';
    return;
  }

  const text = `WIFI:T:WPA;S:${ssid.value};P:${password.value};;`;
  generatedSSID.value = ssid.value;

  qrCode.value = await QRCode.toDataURL(text);

  ssid.value = '';
  password.value = '';

  viewMode.value = 'qr';
}

function downloadQR() {
  if (!qrCode.value) {
    return;
  }

  const link = document.createElement('a');

  link.href = qrCode.value;
  link.download = `wifi-qr-${generatedSSID.value || 'code'}.png`;

  document.body.appendChild(link);
  link.click();
  document.body.removeChild(link);
}
</script>

<template>
  <div
    class="flex flex-col items-center p-3 max-w-md mx-auto w-full overflow-hidden"
  >
    <h1 class="text-3xl font-extrabold text-gray-700 mb-4 text-center">
      WIFI QR GENERATOR
    </h1>

    <div class="relative w-full min-h-[380px]">
      <Transition name="slide-fade" mode="out-in">
        <div
          v-if="viewMode === 'form'"
          key="form-view"
          class="absolute w-full top-0 left-0 flex flex-col items-center"
        >
          <div class="flex flex-col gap-4 my-2 w-full">
            <div class="flex flex-col w-full">
              <label class="text-sm font-semibold mb-1 text-gray-600"
                >SSID/WIFI NAME</label
              >
              <input
                type="text"
                placeholder="SSID"
                v-model="ssid"
                class="bg-white py-2 px-3 rounded-lg outline-none w-full border border-gray-300"
              />
            </div>

            <div class="flex flex-col w-full">
              <label class="text-sm font-semibold mb-1 text-gray-600"
                >PASSWORD</label
              >
              <input
                type="password"
                placeholder="Password"
                v-model="password"
                class="bg-white py-2 px-3 rounded-lg outline-none w-full border border-gray-300"
              />
            </div>
          </div>

          <button
            class="bg-white w-40 py-2 rounded-full font-bold hover:-translate-y-1/10 hover:shadow-xl duration-300 cursor-pointer mt-4"
            @click="generate"
          >
            Generate
          </button>
        </div>
      </Transition>

      <Transition name="slide-fade" mode="out-in">
        <div
          v-if="viewMode === 'qr'"
          key="qr-view"
          class="absolute w-full top-0 left-0 flex flex-col items-center"
        >
          <div
            v-if="qrCode"
            class="mt-4 p-2 rounded-lg flex flex-col justify-center items-center gap-4"
          >
            <img
              :src="qrCode"
              alt="WiFi QR Code"
              class="w-40 h-40 mx-auto border border-gray-300 shadow-xl"
            />

            <button
              class="bg-white w-40 py-2 rounded-full font-bold hover:-translate-y-1/10 hover:shadow-xl duration-300 cursor-pointer"
              @click="downloadQR"
            >
              Download QR
            </button>

            <button
              class="text-sm text-gray-500 mt-2 hover:underline cursor-pointer"
              @click="viewMode = 'form'"
            >
              ← Generate New Code
            </button>
          </div>
        </div>
      </Transition>
    </div>
  </div>
</template>

<style scoped>
.slide-fade-enter-active,
.slide-fade-leave-active {
  transition: all 0.5s ease;
}
.slide-fade-enter-form {
  transform: translateX(100%);
  opacity: 0;
}
.slide-fade-leave-to {
  transform: translateX(-100%);
  opacity: 1;
}
</style>
