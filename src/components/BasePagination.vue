<template id="BasePagination">
  <nav aria-label="Page navigation example">
    <ul class="pagination">
      <li class="page-item">
        <a class="page-link border-0" href="#" aria-label="Previous">
          <span aria-hidden="true">&laquo;</span>
          <span class="sr-only">Previous</span>
        </a>
      </li>
      <li class="page-item" v-for="(item, index) in pageCount" :key="index">
        <a class="page-link border-0 btn" @click="calculater(index)">{{
          index + 1
        }}</a>
      </li>
      <li class="page-item">
        <a class="page-link border-0" href="#" aria-label="Next">
          <span aria-hidden="true">&raquo;</span>
          <span class="sr-only">Next</span>
        </a>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "BasePagination",
  comments: {},
  props: {
    itemCount: Number,
  },
  data() {
    return {
      pageCount: Math.ceil(this.itemCount / 5),
    };
  },
  methods: {
    calculater(index) {
      this.$emit("firstIndex", 5 * index + 0);
      this.$emit("lastIndex", 5 * index + 5);
    },
  },
};
</script>

<style></style>
