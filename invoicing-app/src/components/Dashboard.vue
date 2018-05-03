<script>
  import Header from "./Header";
  import CreateInvoice from "./CreateInvoice";
  import ViewInvoices from "./ViewInvoices";

  export default {
    name: "Dashboard",
    components: {
      Header,
      CreateInvoice,
      ViewInvoices,
    },
    data() {
      return {
        isactive: 'create',
        title: "Invoicing App",
        user: (this.$route.params.user) ? this.$route.params.user : null
      };
    }
  };
</script>

<template>
    <div class="container-fluid" style="padding: 0px;">
        <Header v-bind:user="user"/>
        <template v-if="this.isactive === 'create'">
            <CreateInvoice/>
        </template>
        <template v-else>
            <ViewInvoices/>
        </template>
    </div>
</template>