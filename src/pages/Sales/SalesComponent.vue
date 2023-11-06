<template>
    <DashboardComponent :title="title" :icon="icon">
        <div class="page-content">
            <header class="product-header">
                <p>
                    Search by product/service name, sale id and value
                </p>
                <div class="form-outline">
                    <input type="search" class="form-control" />
                    <button type="button" class="btn btn-primary">
                        <i class="fas fa-search"></i>
                    </button>
                </div>
            </header>
            <div class="product-list">
                <div>
                    <button class="btn"><i class="fa fa-plus" style="color: white;"></i></button>
                </div>
                <table class="table">
                    <thead>
                        <tr>
                            <th scope="col">#</th>
                            <th scope="col">Product/Service Name</th>
                            <th scope="col">Value</th>
                            <th scope="col">Sale Date</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="row in rows" :key="row.id" class="body-row">
                            <td>{{ row.id }}</td>
                            <td>{{ row.name }}</td>
                            <td>{{ row.value }}</td>
                            <td>{{ row.sale_date }}</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </DashboardComponent>
</template>

<script>
import DashboardComponent from '../Dashboard/DashboardComponent.vue';

export default {
    name: 'ProductsComponent',
    components: { DashboardComponent },
    data() {
        return {
            title: "Sales",
            icon: "fa-store",
            rows: [
                {id: 1, name:'product 2', value: "15.00", sale_date: '01-01-2023'},
                {id: 2, name:'service 4', value: "10.00", sale_date: '01-01-2023'},
                {id: 3, name:'service 7', value: "25.00", sale_date: '01-01-2023'},
                {id: 4, name:'product 3', value: "8.00", sale_date: '01-01-2023'},
            ]
        }
    }
}
</script>

<style lang="scss" src="./style.scss" scoped />