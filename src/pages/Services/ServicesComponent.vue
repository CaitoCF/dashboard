<template>
    <DashboardComponent :title="title" :icon="icon">
        <div class="page-content">
            <header class="product-header">
                <p>
                    Search by service name, id or value
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
                            <th scope="col">Service Name</th>
                            <th scope="col">Default Value</th>
                            <th scope="col">Creation Date</th>
                            <th scope="col">Actions</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="row in rows" :key="row.id" class="body-row">
                            <td>{{ row.id }}</td>
                            <td>{{ row.name }}</td>
                            <td>{{ row.value }}</td>
                            <td>{{ row.creation_date }}</td>
                            <td><button class="btn"><i class="fa fa-pen" style="color: white;"></i></button><button class="btn"><i class="fa fa-trash" style="color: white;"></i></button></td>
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
            title: "Services",
            icon: "fa-briefcase",
            rows: [
                {id: 1, name:'service 1', value: "15.00", creation_date: '01-01-2023'},
                {id: 2, name:'service 2', value: "10.00", creation_date: '01-01-2023'},
                {id: 3, name:'service 3', value: "25.00", creation_date: '01-01-2023'},
            ]
        }
    }
}
</script>

<style lang="scss" src="./style.scss" scoped />