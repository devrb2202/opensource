 <template>
    <v-container>
        <v-row class="d-flex justify-center align-center --login-height" no-gutters wrap xs="12">
            <v-col cols="12" xl="5" sm="10" md="6" lg="6" xll="1">
                <v-card class="elevation-6 pa-12 rounded-lg">
                    <div class="text-center">
                        <v-icon size="70">mdi-lightning-bolt</v-icon>
                    </div>
                    <v-card-title>Login</v-card-title>
                    <v-card-text>
                        <v-text-field label="Username"
                          variant="outlined"
                          prepend-inner-icon="mdi-account"
                          color="orange-lighten-1"
                          placeholder="Enter your username"

                        >
                        </v-text-field>

                        <!-- NOTE!! -->
                        <!-- USE NUXTLINK INSTEAD -->
                        <!-- <div class="text-subtitle-1 text-medium-emphasis d-flex align-center justify-end">
                            <a
                            class="text-caption text-decoration-none text-blue"
                            href="#"
                            rel="noopener noreferrer"
                            target="_blank"
                            >
                            Forgot login password?
                            </a>
                        </div> -->

                        <v-text-field label="Password" 
                         variant="outlined"
                         prepend-inner-icon="mdi-lock"
                        :append-inner-icon="visible ? 'mdi-eye-off' : 'mdi-eye'"
                        :type="visible ? 'text' : 'password'"
                         @click:append-inner="visible = !visible"
                         color="orange-lighten-1"
                         placeholder="Enter your password"
                        >
                        </v-text-field>

                         <!-- NOTE!! -->
                        <!-- USE NUXTLINK INSTEAD -->
                        <div class="text-subtitle-1 text-medium-emphasis d-flex align-center justify-end mb-5">
                            <a
                            class="text-caption text-decoration-none text-blue"
                            href="#"
                            rel="noopener noreferrer"
                            target="_blank"
                            >
                            Forgot login password?
                            </a>
                        </div>

                        <!-- <v-card
                        class="mb-5 mt-5"
                        color="surface-variant"
                        variant="tonal"
                        >
                            <v-card-text class="text-medium-emphasis text-caption">
                                {{ loginMessage }}
                            </v-card-text>
                        </v-card> -->
                        <v-btn @click="login" color="orange-lighten-1" block>Login</v-btn>
                    </v-card-text>

                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>

<script setup>

const visible = ref(false)

const loginMessage = ref(` Warning: After 3 consecutive failed login attempts, you account will be 
temporarily locked for three hours. If you must login now, you can also click "Forgot login password?" 
below to reset the login password.`)


</script>


<style scoped>

.--login-height {
    margin-top: 10%;
}
.--button-color {
    color: white;
}

</style>
