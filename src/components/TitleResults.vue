<template>
    <div class="root">
        <p class="filter-item-title-number">Showing {{ filteredTitles.length }} results for "{{ query }}"</p>
        <ul class="filter-list-section ">
            <li v-for="title in filteredTitles" v-bind:key="title.Page" class="filter-list-item ">
                {{ title.Name }}
            </li>
        </ul>
    </div>
</template>

<script>
import { computed } from "vue";
export default {
    props: {
        query: String,
    },
    setup(props) {
        var titles = [
            {
                Name: "Do something nice for someone I care about",
               
            },
            {
                Name: "Contribute code or a monetary donation to an open-source software project",
                
            },
            {
                Name: "Take a class at local community center that interests you",
                
            },
             {
                Name: "Whatever the mind of man can conceive and believe, it can achieve",
               
            },
            {
                Name: "Two roads diverged in a wood, and I—I took the one less traveled by, And that has made all the difference",
                
            },
            {
                Name: "I attribute my success to this: I never gave or took any excuse",
                
            },
             {
                Name: "We must balance conspicuous consumption with conscious capitalism.",
               
            }
        ]
        const filteredTitles = computed(() => {
            return titles.filter((s) =>
                s.Name.toLowerCase().includes(props.query.toLowerCase())
            );
        });
        return {
            filteredTitles,
        };
    },
};
</script>

<style>
.root{
   
    width: 40%;
    margin: auto;

}
.filter-list-item {
     padding: 15px;
    border: 1px solid #ccc;
    border-bottom: none; 
    list-style-type:none;
}
.filter-list-section {
    padding-top: 20px;
    height: 300px;
    overflow-y: scroll;
}
.filter-item-title-number {
    text-align: right;
}
.filter-list-item:last-child {
    border-bottom: 1px solid #ccc;
}

</style>
