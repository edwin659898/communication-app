<template>
 
  <div v-if="links.length > 3">
    <div class="flex flex-wrap -mb-1">
                                      <div class="pagination-row">
                                        <select v-model="itemsPerPage">
                                          <option value="25">25</option>
                                          <option value="50">50</option>
                                          <option value="100">100</option>
                                          <option value="All">All</option>
                                        </select>
                                      </div>
      <template v-for="(link, k) in links" :key="k">
        <div v-if="link.url === null"  class="mr-1 mb-1 px-4 py-3 text-sm leading-4 text-gray-400 border rounded" v-html="link.label" />
        <Link v-else class="mr-1 mb-1 px-4 py-3 text-xs leading-2 border rounded hover:bg-white focus:border-indigo-500 focus:text-indigo-500" :class="{ 'bg-blue-700 text-white': link.active }" :href="link.url" v-html="link.label" />

      </template>
                                    
                                        
                                            <!-- <span v-for="perPageOption in [50, 200, 500, 'All']" :key="perPageOption">
                                            <button class="rounded-lg bg-green-700 px-2 py-2 h-8 text-white text-xs hover:bg-blue-500"
                                                @click="changePerPage(perPageOption)"
                                            >{{ perPageOption }}</button>
                                            </span> -->
      </div>                                 
    
  </div>
                                       

</template>
  
<script>

import { Link } from '@inertiajs/inertia-vue3';
export default {
  components: {
      Link      
  },
  props: {
    links: Array,
  },
  // method: {
  //    changePerPage(newPerPage){
  //     this.perPage = newPerPage;
  //    }
  // },
}
</script> 