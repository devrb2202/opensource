<template>
    <div class="text-center">
        <v-menu
         transition="scale-transition"
        >
        <template v-slot:activator="{ props }">
            <v-btn
            v-bind="props"
            append-icon="mdi-menu-down"
            
            >
                Account
            </v-btn>
        </template>

            <v-list>
                <v-list-item
                    v-for="(item, index) in items"
                    :key="index"
                    :to="item.to"
                    >
                    <v-list-item-title>{{ item.title }}</v-list-item-title>
                </v-list-item>
                
            </v-list>
        </v-menu>
    </div>
</template>

<script>

export default {
    data: () => ({
        items: [
        { title: 'Login' , to: '/login'},
        { title: 'Register', to: '/register' },
        ],
    }),
}

</script>