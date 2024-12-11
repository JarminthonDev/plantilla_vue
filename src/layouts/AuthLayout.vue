<template>
  <!--begin::Authentication Layout -->
  <div class="d-flex flex-column flex-lg-row flex-column-fluid">
    <!--begin::Body-->
    <div
      class="d-flex flex-column flex-lg-row-fluid w-lg-50 p-10 order-2 order-lg-1"
    >
      <!--begin::Form-->
      <div class="d-flex flex-center flex-column flex-lg-row-fluid">
        <!--begin::Wrapper-->
        <div class="<?php echo $params['wrapperClass']?> p-10">
          <router-view></router-view>
        </div>
        <!--end::Wrapper-->
      </div>
      <!--end::Form-->

      <!--begin::Footer-->
   
      <!--end::Footer-->
    </div>
    <!--end::Body-->

    <!--begin::Aside-->
    <div
      class="d-flex flex-lg-row-fluid w-lg-75 bgi-size-cover bgi-position-center order-1 order-lg-2"
      style="background-image: url('media/logos/custom-1.jpg')"
    >
      <!--begin::Content-->
      <div
        class="d-flex flex-column flex-center py-7 py-lg-15 px-5 px-md-15 w-100"
      >
        <!--begin::Logo-->
        <router-link to="/" class="mb-0 mb-lg-12">
          <!-- <img
            alt="Logo"
            src="media/logos/FreyaLogo.png"
            class="h-60px h-lg-75px"
          /> -->
          <br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
        </router-link>
        <!--end::Logo-->
      </div>
      <!--end::Content-->
    </div>
    <!--end::Aside-->
  </div>
  <!--end::Authentication Layout -->
</template>

<script>
import { defineComponent, onMounted } from "vue";
import LayoutService from "@/core/services/LayoutService";
import { useStore } from "vuex";
import { Actions } from "@/store/enums/StoreEnums";

export default defineComponent({
  name: "auth-layout",
  components: {},
  setup() {
    const store = useStore();

    onMounted(() => {
      LayoutService.emptyElementClassesAndAttributes(document.body);

      store.dispatch(Actions.ADD_BODY_CLASSNAME, "app-blank");

      store.dispatch(Actions.ADD_BODY_CLASSNAME, "bg-body");
    });
  },
});
</script>
