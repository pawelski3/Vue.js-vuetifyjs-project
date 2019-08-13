<template>
  <v-layout>
    <v-navigation-drawer v-model="open" absolute right>
      <v-list-item avatar>
        <v-list-item-avatar>
          <img src="https://randomuser.me/api/portraits/men/67.jpg" alt="image" />
        </v-list-item-avatar>
        <v-list-item-content>pawelgawel.c0.pl</v-list-item-content>
      </v-list-item>
      <v-divider></v-divider>
      <v-form>
        <v-container>
          <v-flex xs12>
            <img :src="imageUrl" alt height="150px" />
            <v-text-field
              label="Select an image"
              v-model="imageName"
              prepend-icon="attach-file"
              @click="pickFile()"
            ></v-text-field>
            <input
              type="file"
              style="display:none"
              ref="image"
              accept="image/*"
              @change="onFilePicked"
            />

            <v-btn :loading="loading" :disabled="!imageFile" @click="uploadFile()">
              Set as background
              <v-icon right dark>cloud_upload</v-icon>
            </v-btn>
          </v-flex>
        </v-container>
      </v-form>
    </v-navigation-drawer>
  </v-layout>
</template>
<script>
export default {
  name: "moreOptions",
  data: () => ({
    loading: false,
    open: true,
    imageName: "",
    imageUrl: "",
    imageFile: ""
  }),
  methods: {
    pickFile() {
      this.$refs.image.click();
    },
    onFilePicked(e) {
      const files = e.target.files;
      if(files[0]!==undefined){
        this.imageName=files[0].name;
        if(this.imageName.lastIndexOf(".")<=0){
          return;
        }
        const fr=new FileReader();
        fr.readAsDataURL(files[0]);
        fr.addEventListener("load",()=>{
          this.imageUrl=fr.result;
          this.imageFile=files[0];
        })

      }else{
        this.imageName='';
        this.imageFile='';
        this.imageUrl='';
      }
    },
    uploadFile() {
      console.log(this.imageFile);
    }
  }
};
</script>