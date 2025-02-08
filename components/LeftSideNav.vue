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
            
           
            >
            <!-- to="/dashboard/users" -->
        </v-list-item>
        </template>

        <v-list-item
            v-for="([title, icon, to], i) in admins"
            :key="i"
            :prepend-icon="icon"
            :title="title"
            :value="title"
            :to="to"
        ></v-list-item>
        </v-list-group>

        <!-- STAND BY -->
        <!-- <v-list-group value="Actions">
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
        </v-list-group> -->

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
                <!--     to="/dashboard/products" -->
                </v-list-item>
                
            </template>

            <v-list-item
            v-for="([title, icon, to], i) in items"
            :key="i"
            :prepend-icon="icon"
            :title="title"
            :value="title"
            :to="to"
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
                <!-- to="/dashboard/reports" -->
                </v-list-item>
                
            </template>

            <v-list-item
            v-for="([title, icon, to], i) in files"
            :key="i"
            :prepend-icon="icon"
            :title="title"
            :value="title"
            :to="to"
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
        ['Management', 'mdi-account-multiple-outline','/dashboard/users/managements'],
        ['Settings', 'mdi-cog-outline','/dashboard/users/settings'],
   
    ],
    // cruds: [
    //     ['Create', 'mdi-plus-outline',],
    //     ['Read', 'mdi-file-outline'],
    //     ['Update', 'mdi-update'],
    //     ['Delete', 'mdi-delete'],
    // ],

    // 2nd group products
    items: [
        ['Add Product', 'mdi-plus-outline','/dashboard/products/add'],
        ['View Products', 'mdi-file-outline', '/dashboard/products/view'],
        ['Update Product', 'mdi-update','/dashboard/products/update'],
        ['Delete Product', 'mdi-delete','/dashboard/products/delete'],
    ],
    // 3rd group
    files: [
        ['Add File', 'mdi-plus-outline', '/dashboard/reports/add'],
        ['View Files', 'mdi-file-outline','/dashboard/reports/view'],
        ['Update File', 'mdi-update','/dashboard/reports/update'],
        ['Delete File', 'mdi-delete','/dashboard/reports/delete'],
    ],
    }),
}
</script>