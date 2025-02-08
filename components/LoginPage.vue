<!-- <template>
    <v-container>
      <v-row class="d-flex justify-center align-center --login-height">
        <v-col cols="10" sm="4">
          <v-card class="elevation-6 pa-12 rounded-lg">
            <div class="text-center">
              <v-icon size="70">mdi-lightning-bolt</v-icon>
            </div>
            <v-card-title>Login</v-card-title>
            <v-card-text>
              <v-text-field
                label="Username"
                variant="outlined"
                prepend-inner-icon="mdi-account"
                color="orange-lighten-1"
                placeholder="Enter your username"
                v-model="username"
              ></v-text-field>
  
               Password Field 
              <v-text-field
                label="Password"
                variant="outlined"
                prepend-inner-icon="mdi-lock"
                :append-inner-icon="visible ? 'mdi-eye-off' : 'mdi-eye'"
                :type="visible ? 'text' : 'password'"
                @click:append-inner="visible = !visible"
                color="orange-lighten-1"
                placeholder="Enter your password"
                v-model="password"
              ></v-text-field>
  
              < Password Reset Link 
              <div class="text-subtitle-1 text-medium-emphasis d-flex align-center justify-end">
                <NuxtLink to="/reset-password" class="text-caption text-decoration-none text-blue">
                  Forgot login password?
                </NuxtLink>
              </div>
  
               Error or Warning Message 
              <v-card class="mb-5 mt-5" color="surface-variant" variant="tonal">
                <v-card-text class="text-medium-emphasis text-caption" v-if="errorMessage">
                  {{ errorMessage }}
                </v-card-text>
                <v-card-text class="text-medium-emphasis text-caption" v-else>
                  {{ loginMessage }}
                </v-card-text>
              </v-card>

               Login Button with Loading
              <v-btn :loading="loading" @click="loginUser" color="orange-lighten-1" block>Login</v-btn>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  // Reactive references
  const visible = ref(false);
  const loading = ref(false);
  const loginMessage = ref(
    `Warning: After 3 consecutive failed login attempts, your account will be temporarily locked for three hours. If you must login now, you can also click "Forgot login password?" below to reset the login password.`
  );
  const username = ref('');
  const password = ref('');
  const errorMessage = ref(null);
  const loginSuccess = ref(false);
  const userInfo = ref(null);
  
  // Fetch list of users from the users API to validate credentials
  const fetchUsers = async () => {
    try {
      const res = await fetch('https://fakestoreapi.com/users');
      if (!res.ok) {
        throw new Error('Failed to fetch users');
      }
      const users = await res.json();
      return users;
    } catch (error) {
      console.error('Error fetching users:', error.message);
      return [];
    }
  };
  
  // Check if the user is already logged in via localStorage (with the token)
  const authToken = localStorage.getItem('authToken');
  if (authToken) {
    // Optionally, you can fetch user info with the token or redirect
    console.log('User is already logged in');
  }
  
  // Function to handle the login
  const loginUser = async () => {
    loading.value = true;
    errorMessage.value = null;
    loginSuccess.value = false;
  
    try {
      // Validate username and password against users API
      const users = await fetchUsers();
      const validUser = users.find(user => user.username === username.value && user.password === password.value);
  
      if (!validUser) {
        throw new Error('Invalid credentials');
      }
  
      // If valid user, attempt to login with valid credentials
      const res = await fetch('https://fakestoreapi.com/auth/login', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
          username: username.value,
          password: password.value,
        }),
      });
  
      // Handle login failure
      if (!res.ok) {
        throw new Error('Invalid credentials or login failed');
      }
  
      // Parse the response JSON
      const json = await res.json();
      userInfo.value = json;
      loginSuccess.value = true;
  
      console.log('Login successful:', json);
  
      // Store the token in localStorage for persistence
      localStorage.setItem('authToken', json.token);
  
      // Optionally, redirect the user or fetch more data
      // e.g., router.push('/dashboard') or similar logic
    } catch (error) {
      errorMessage.value = error.message;
      console.error('Login Error:', error.message);
    } finally {
      loading.value = false;
    }
  };
  </script> -->
  
  <!-- <style scoped>
  .--login-height {
    margin-top: 10%;
  }
  .--button-color {
    color: white;
  }
  </style> -->
  

  <template>
    <v-container>
        <v-row class="d-flex justify-center align-center --login-height">
            <v-col cols="10" sm="4">
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
                        <div class="text-subtitle-1 text-medium-emphasis d-flex align-center justify-end">
                            <a
                            class="text-caption text-decoration-none text-blue"
                            href="#"
                            rel="noopener noreferrer"
                            target="_blank"
                            >
                            Forgot login password?
                            </a>
                        </div>

                        <v-card
                        class="mb-5 mt-5"
                        color="surface-variant"
                        variant="tonal"
                        >
                            <v-card-text class="text-medium-emphasis text-caption">
                                {{ loginMessage }}
                            </v-card-text>
                        </v-card>
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
