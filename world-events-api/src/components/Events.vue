<template>
<div class="card mx-auto  text-center" style="width: 18rem;">
  <div class="card-body ">
    <h5 class="card-title">Card title</h5>
    <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
    <p class="card-text">Event Description</p>
    <br>
    <br>
  </div>

        <div>
            {{ res }}
        </div>
    </div>
    <!-- Look at EventCard to see how each is wrapped -->
</template>

<script>
import axios from "axios";
export default {
    data() {
        return {
            res: [],
        };
    },
    name: "App",
    methods: {
        // The get method called by the function
        onGet() {
            axios
                .get("https://jsonplaceholder.typicode.com/todos")
                .then((res) => {
                    console.log(res);
                    // using stringify to beautify the output
                    this.res = JSON.stringify(response.data);
                })
                .catch((errors) => {
                    console.log(errors); // Errors
                });
        },
    },
};
</script>