<template>
  <v-container fill-height>
    <v-layout allign-center justify-center>
      <v-flex xs12 sm8 md4>
        <v-card class="elevation-12">
          <v-toolbar dark color="blue">
            <v-toolbar-title>Signup form</v-toolbar-title>
          </v-toolbar>
          <v-card-text>
            <v-form>
              <v-alert
                :value="true"
                color="error"
                icon="warning"
              >This user already exist, try a different set of data
              </v-alert>
<v-text-field

name="login"
label="Login"
:rules="[rules.required]"
>
</v-text-field>


<v-text-field

name="email"
label="Email"
:rules="[rules.required,rules.email]"
>
</v-text-field>


<v-text-field

name="password"
label="Password"
:rules="[rules.required]"
type="password"
v-model="password"
>
</v-text-field>

<v-text-field

name="password"
label="Confirm Password"
:rules="[rules.required]"
type="password"
v-model="confirm_password"
:error="!valid()"
>
</v-text-field>

<v-divider light></v-divider>
<v-card-actions>
    <v-btn rounded color="black" dark>Sign in</v-btn>
    <v-spacer></v-spacer>
    <v-btn rounded color="success">
Register

    </v-btn>
</v-card-actions>






            </v-form>
          </v-card-text>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default{
    name:"signup",
    data:()=>({
        password:"",
        confirm_password:"",
        rules:{
            required:value=>!!value || "Required",
            email:value=>{
                const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
return pattern.test(value)||"Invalid e-mail";

            }
        }
    }),

    methods:{
        valid(){
            return this.password===this.confirm_password;
        }
    }

}
</script>