<template>
    <v-container>
        <v-row class="d-flex justify-center align-center --login-height">
            <v-col cols="12" sm="4">
                <v-card class="elevation-6 pa-12 rounded-lg">
                    <v-card-title>Account Registration</v-card-title>
                    <v-card-text>
                        <v-text-field label="Email"
                          variant="outlined"
                          prepend-inner-icon="mdi-email"
                          color="orange-lighten-1"
                          placeholder="Your Email"
                        >
                        </v-text-field>
                        <v-text-field label="Username"
                          variant="outlined"
                          prepend-inner-icon="mdi-account"
                          color="orange-lighten-1"
                          placeholder="Your Username"
                        >
                        </v-text-field>
                        <v-text-field label="Password" 
                         type="password"
                         variant="outlined"
                         prepend-inner-icon="mdi-lock"
                         color="orange-lighten-1"
                         placeholder="Your Password"

                        >
                        </v-text-field>
                        <v-text-field label="Confirm Password" 
                         type="password"
                         variant="outlined"
                         prepend-inner-icon="mdi-lock"
                         color="orange-lighten-1"
                         placeholder="Your Confirm Password"
                        >
                        </v-text-field>
                        <v-btn @click="login" color="orange-lighten-1" block>Register</v-btn>
                    </v-card-text>
                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>

<script setup>

</script>


<style scoped>

.--login-height {
    margin-top: 8%;
}
.--button-color {
    color: white;
}

</style>

