<template>
    <div>
        <span style="font-size:30px;cursor:pointer" v-on:click="openNav">&#9776;</span>
        <div id="leftsidenav" class="sidenav">
            <p style="font-size:12px;cursor:pointer" v-on:click="closeNav"><em>Close Nav</em></p>
            <p><em>Company: {{ company }} </em></p>
            <h3>Welcome, {{ name }}</h3>
            <p class="clickable" v-on:click="setActive('create')">Create Invoice</p>
            <p class="clickable" v-on:click="setActive('view')">View Invoices</p>
        </div>
    </div>
</template>

<script>
  export default {
    name: "SideNav",
    props: ["name", "company"],
    methods: {
      setActive(option) {
        this.$parent.$parent.isactive = option;
      },
      openNav() {
        document.getElementById("leftsidenav").style.width = "20%";
      },
      closeNav() {
        document.getElementById("leftsidenav").style.width = "0%";
      }
    }
  };
</script>