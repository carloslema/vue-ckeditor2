<template>
  <div id="app" class="app">
    <a
      href="https://github.com/dangvanthanh/vue-ckeditor2"
      target="_blank"
      aria-label="View source on Github"
      class="github-corner"
      style="fill: rgb(21, 21, 19); color: rgb(255, 255, 255); position: absolute; top: 0px; border: 0px; right: 0px;">
      <svg
        width="80"
        height="80"
        viewBox="0 0 250 250"
        aria-hidden="true" >
        <path d="M0,0 L115,115 L130,115 L142,142 L250,250 L250,0 Z"></path>
        <path d="M128.3,109.0 C113.8,99.7 119.0,89.6 119.0,89.6 C122.0,82.7 120.5,78.6 120.5,78.6 C119.2,72.0 123.4,76.3 123.4,76.3 C127.3,80.9 125.5,87.3 125.5,87.3 C122.9,97.6 130.6,101.9 134.4,103.2" fill="currentColor" class="octo-arm" style="transform-origin: 130px 106px 0px;"></path><path d="M115.0,115.0 C114.9,115.1 118.7,116.5 119.8,115.4 L133.7,101.6 C136.9,99.2 139.9,98.4 142.2,98.6 C133.8,88.0 127.5,74.4 143.8,58.0 C148.5,53.4 154.0,51.2 159.7,51.0 C160.3,49.4 163.2,43.6 171.4,40.1 C171.4,40.1 176.1,42.5 178.8,56.2 C183.1,58.6 187.2,61.8 190.9,65.4 C194.5,69.0 197.7,73.2 200.1,77.6 C213.8,80.2 216.3,84.9 216.3,84.9 C212.7,93.1 206.9,96.0 205.4,96.6 C205.1,102.4 203.0,107.8 198.3,112.5 C181.9,128.9 168.3,122.5 157.7,114.1 C157.9,116.9 156.7,120.9 152.7,124.9 L141.0,136.5 C139.8,137.7 141.6,141.9 141.8,141.8 Z" fill="currentColor" class="octo-body"></path>
      </svg>
    </a>
    <h1 class="mt-3 mb-6 text-2xl">Ckeditor 4 using with Vue.js</h1>
    <div class="mb-8">
      <h2 class="text-base mb-3">
        <span class="h-6 w-6 inline-block align-middle">
          <svg viewBox="0 0 38 38" xmlns="http://www.w3.org/2000/svg" fill-rule="evenodd" clip-rule="evenodd" stroke-linejoin="round" stroke-miterlimit="1.5"><g fill="#888" stroke="#444" stroke-width="1.5"><path d="M12.029.98c-1.395-.507-3.296-.148-4.247.803-.951.951-.592 2.134.803 2.642M8.585 4.425l15.51 5.645M12.029.98l18.365 6.685" /><path d="M25.351 10.606L7.25 3.613l.007 26.258 18.094 6.669V10.606z"/><path d="M11.342 12.128l9.766 3.351M11.342 18.128l9.766 3.351M11.342 24.128l9.766 3.351" stroke-linecap="round"/><path d="M29.805 7.231v24.544"/></g></svg>
        </span>
        <span class="inline-block align-middle">Classic Editor</span>
      </h2>
      <div>
        <vue-ckeditor
          v-model="classic.content"
          :config="classic.config"
          @blur="onBlurClassic($event)"
          @focus="onFocusClassic($event)"/>
      </div>
    </div>
    <div class="mb-8">
      <h2 class="text-base mb-3">
        <span class="h-6 w-6 inline-block align-middle">
          <svg viewBox="0 0 38 38" xmlns="http://www.w3.org/2000/svg" fill-rule="evenodd" clip-rule="evenodd" stroke-linejoin="round" stroke-miterlimit="1.5"><g fill="#888" stroke="#444" stroke-width="1.5"><path d="M12.029.98c-1.395-.507-3.296-.148-4.247.803-.951.951-.592 2.134.803 2.642M8.585 4.425l15.51 5.645M12.029.98l18.365 6.685"/><path d="M25.351 10.606L7.25 3.613l.007 26.258 18.094 6.669V10.606z"/><path d="M11.342 12.128l9.766 3.351M11.342 18.128l9.766 3.351M11.342 24.128l9.766 3.351" stroke-linecap="round"/><path d="M29.805 7.231v24.544"/></g></svg>
        </span>
        <span class="inline-block">Inline Editor</span>
      </h2>
      <div>
        <vue-ckeditor v-model="inline.content" :config="inline.config" types="inline" />
      </div>
    </div>
    <div class="mb-2">
      <h2 class="text-base mb-3">
        <span class="h-6 w-6 inline-block align-middle">
          <svg viewBox="0 0 38 38" xmlns="http://www.w3.org/2000/svg" fill-rule="evenodd" clip-rule="evenodd" stroke-linejoin="round" stroke-miterlimit="1.5"><g fill="#888" stroke="#444" stroke-width="1.5"><path d="M12.029.98c-1.395-.507-3.296-.148-4.247.803-.951.951-.592 2.134.803 2.642M8.585 4.425l15.51 5.645M12.029.98l18.365 6.685"/><path d="M25.351 10.606L7.25 3.613l.007 26.258 18.094 6.669V10.606z"/><path d="M11.342 12.128l9.766 3.351M11.342 18.128l9.766 3.351M11.342 24.128l9.766 3.351" stroke-linecap="round"/><path d="M29.805 7.231v24.544"/></g></svg>
        </span>
        <span class="inline-block align-middle">Multiple Plugins</span>
      </h2>
      <div>
        <vue-ckeditor v-model="multiplePlugins.content" :config="multiplePlugins.config" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      classic: {
        content: 'The three greatest things you learn from traveling',
        config: {
          toolbar: [
            ['Bold', 'Italic', 'Underline', 'Strike', 'Subscript', 'Superscript']
          ],
          height: 200
        }
      },
      inline: {
        content: 'Monthly travel news and inspiration',
        config: {
          toolbar: [
            ['Bold', 'Italic', 'Underline', 'Strike', 'Subscript', 'Superscript']
          ],
          height: 200
        }
      },
      multiplePlugins: {
        content:`
          <p>Use multiple plugins image2, autogrow, easyimage and placeholder</p>
          <ul><li>Male / Female</li><li>Graduate of [[Internal Auditing]] / Accountancy or any related Business course</li><li>With at least minimum of 6 months experience on the same field but not necessary</li><li>With above average of communication skills in both oral and written English</li><li>Proficient in MS Office</li><li>Willing to be assigned in Pasig City and willing to do periodic travels to Batangas, Laguna, Cavite and Clark areas</li><li>Open to all fresh graduates&nbsp;</li></ul>
          <figure class="easyimage easyimage-full">
            <img alt="Three Monks walking on ancient temple." width="912" sizes="100vw" src="https://cdn.dribbble.com/users/458522/screenshots/4615441/attachments/1043210/deadpool_love_add.jpg" />
            <figcaption></figcaption>
          </figure>
        `,
        config: {
          toolbar: [
            ['Image', 'EasyImageUpload', 'CreatePlaceholder']
          ],
          height: 200,
          extraPlugins: 'image2,autogrow,xml,ajax,cloudservices,balloonpanel,balloontoolbar,imagebase,easyimage,placeholder',
          emovePlugins: 'image',
          cloudServices_tokenUrl: 'https://33372.cke-cs.com/token/dev/kquv5QAPjvSD8p7GYFSFa3uKP6OcikCtjcyDpqW1Aqy3eotwe2pPLVdAjJVu',
          cloudServices_uploadUrl: 'https://33372.cke-cs.com/easyimage/upload/',
          easyimage_styles: {
            gradient1: {
              group: 'easyimage-gradients',
              attributes: {
                  'class': 'easyimage-gradient-1'
              },
              label: 'Blue Gradient',
              icon: 'https://sdk.ckeditor.com/../samples/assets/easyimage/icons/gradient1.png',
              iconHiDpi: 'https://sdk.ckeditor.com/../samples/assets/easyimage/icons/hidpi/gradient1.png'
            },
            gradient2: {
              group: 'easyimage-gradients',
              attributes: {
                  'class': 'easyimage-gradient-2'
              },
              label: 'Pink Gradient',
              icon: 'https://sdk.ckeditor.com/../samples/assets/easyimage/icons/gradient2.png',
              iconHiDpi: 'https://sdk.ckeditor.com/../samples/assets/easyimage/icons/hidpi/gradient2.png'
            },
            noGradient: {
              group: 'easyimage-gradients',
              attributes: {
                  'class': 'easyimage-no-gradient'
              },
              label: 'No Gradient',
              icon: 'https://sdk.ckeditor.com/../samples/assets/easyimage/icons/nogradient.png',
              iconHiDpi: 'https://sdk.ckeditor.com/../samples/assets/easyimage/icons/hidpi/nogradient.png'
            }
          },
          easyimage_toolbar: ['EasyImageFull', 'EasyImageSide', 'EasyImageGradient1', 'EasyImageGradient2', 'EasyImageNoGradient', 'EasyImageAlt'],
          autoGrow_minHeight: 200,
          autoGrow_maxHeight: 600
        }
      }
    };
  }
};
</script>

<style scoped>
body {
  color: #444;
  font-family: Helvetica, sans-serif;
  margin: 0;
}

.app {
  width: 60em;
  margin: 0 auto;
}

.ckeditor {
  font-size: 13px;
}
</style>
