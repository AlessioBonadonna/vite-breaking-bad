<template>
    <div class="cont-select mb-4">
        <form class="row row-cols-lg-auto g-3 align-items-center" @submit.prevent='seachcharater'>


            <div class="col-12">
                <select class="form-select" id="inlineFormSelectPref" v-model="seach">
                    <option selected value="">Choose...</option>
                    <option :value="category" v-for="(category, index) in StatusOptions" :key="index">{{ category }}
                    </option>


                </select>
            </div>

            <div class="col-12">
                <button type="search" class="btn btn-primary">seach</button>
            </div>

            <div class="col-12">
                <button type="reset" class="btn btn-danger" @click="resetseach">reset</button>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    name: 'SeachBarComponent',
    data() {
        return {
            StatusOptions: [
                'Breaking Bad',
                'Better Call Saul'
            ],
            seach: '',

        }
    },
    methods: {
        seachcharater() {
            this.$emit('filterchar', this.seach)
            console.log(this.seach)
        },
        resetseach() {
            this.seach = '',
                this.$emit('filterchar', this.seach)

        }

    }

}
</script>

<style lang="scss" scoped>
.form-floating {
    text-align: center;
}
</style>