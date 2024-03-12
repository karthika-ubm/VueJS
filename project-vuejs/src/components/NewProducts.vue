<template>
  <div class="col-md-12">
    <div class="card table-card">
      <div class="card-header">
        <h5>New Products</h5>
        <div class="card-header-right">
                                                                <ul class="list-unstyled card-option">
                                                                    <li class="first-opt">
                                                                        <i class="feather icon-chevron-left open-card-option"></i>
                                                                    </li>
                                                                    <li>
                                                                        <i class="feather icon-maximize full-card"></i>
                                                                    </li>
                                                                    <li>
                                                                        <i class="feather icon-minus minimize-card"></i>
                                                                    </li>
                                                                    <li>
                                                                        <i class="feather icon-refresh-cw reload-card"></i>
                                                                    </li>
                                                                    <li>
                                                                        <i class="feather icon-trash close-card"></i>
                                                                    </li>
                                                                    <li>
                                                                        <i class="feather icon-chevron-left open-card-option"></i>
                                                                    </li>
                                                                </ul>
                                                            </div>
      </div>
      <div class="card-block p-b-0">
        <div class="table-responsive">
          <table class="table table-hover m-b-0">
            <thead>
              <tr>
                <th>Name</th>
                <th>Product Code</th>
                <th>Customer</th>
                <th>Status</th>
                <th>Rating</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(product, index) in newProducts" :key="index">
                <td>{{ product.name }}</td>
                <td>{{ product.product_code }}</td>
                <td>{{ product.customer }}</td>
                <td>
                  <label :class="getStatusClass(product.status)">{{ product.status }}</label>
                </td>
                <td>
                  <span v-for="i in product.rating" :key="i">
                    <i class="fa fa-star f-12 text-c-yellow"></i>
                  </span>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// Import the JSON data
import newProductsData from '../assets/jsons/New_Products.json';

export default {
  data() {
    return {
      newProducts: newProductsData.new_products
    };
  },
  methods: {
    getStatusClass(status) {
      return status === 'In Stock' ? 'label label-success' : 'label label-danger';
    }
  }
};
</script>
