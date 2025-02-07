<template>

<v-list v-model:opened="open">
    <v-list-item prepend-icon="mdi-cart" class="mb-5 text-h5">Your Shop Application</v-list-item>

    <v-list-group value="Users">
        <template v-slot:activator="{ props }">
        <v-list-item
            v-bind="props"
            prepend-icon="mdi-account-circle"
            title="Users"
        >
        </v-list-item>
        </template>

        <v-list-group value="Admin">
        <template v-slot:activator="{ props }">
            <v-list-item
            v-bind="props"
            title="Admin"
            ></v-list-item>
        </template>

        <v-list-item
            v-for="([title, icon], i) in admins"
            :key="i"
            :prepend-icon="icon"
            :title="title"
            :value="title"
        ></v-list-item>
        </v-list-group>

        <v-list-group value="Actions">
        <template v-slot:activator="{ props }">
            <v-list-item
            v-bind="props"
            title="Actions"
            ></v-list-item>
        </template>

        <v-list-item
            v-for="([title, icon], i) in cruds"
            :key="i"
            :prepend-icon="icon"
            :title="title"
            :value="title"
        ></v-list-item>
        </v-list-group>
    </v-list-group>

    <!-- second group -->

    <v-list-group>
        <template v-slot:activator="{ props }">
            <v-list-item
            v-bind="props"
            prepend-icon="mdi-view-dashboard-outline"
            title="Products"
            >
            </v-list-item>
        </template>

        <v-list-group value="Options">
            <template v-slot:activator="{ props }">
                <v-list-item
                v-bind="props"
                title="Options"
                >
                </v-list-item>
                
            </template>

            <v-list-item
            v-for="([title, icon], i) in items"
            :key="i"
            :prepend-icon="icon"
            :title="title"
            :value="title"
            >
            
            </v-list-item>

        </v-list-group>
    </v-list-group>

    <!-- 3rd Group -->

    <v-list-group>
        <template v-slot:activator="{ props }">
            <v-list-item
            v-bind="props"
            prepend-icon="mdi-chart-scatter-plot-hexbin"
            title="Reports"
            >
            </v-list-item>
        </template>

        <v-list-group value="Files">
            <template v-slot:activator="{ props }">
                <v-list-item
                v-bind="props"
                title="Files"
                >
                </v-list-item>
                
            </template>

            <v-list-item
            v-for="([title, icon], i) in files"
            :key="i"
            :prepend-icon="icon"
            :title="title"
            :value="title"
            >
            
            </v-list-item>

        </v-list-group>
    </v-list-group>
    
</v-list>
<!-- </div> -->
</template>
<script>
export default {
    data: () => ({
    open: ['Users', 'Products', 'Reports'],
    // 1st group
    admins: [
        ['Management', 'mdi-account-multiple-outline'],
        ['Settings', 'mdi-cog-outline'],
    ],
    cruds: [
        ['Create', 'mdi-plus-outline'],
        ['Read', 'mdi-file-outline'],
        ['Update', 'mdi-update'],
        ['Delete', 'mdi-delete'],
    ],
    // 2nd group
    items: [
        ['Add Product', 'mdi-plus-outline'],
        ['View Products', 'mdi-file-outline'],
        ['Update Product', 'mdi-update'],
        ['Delete Product', 'mdi-delete'],
    ],
    // 3rd group
    files: [
        ['Add File', 'mdi-plus-outline'],
        ['View Files', 'mdi-file-outline'],
        ['Update File', 'mdi-update'],
        ['Delete File', 'mdi-delete'],
    ],
    }),
}
</script>