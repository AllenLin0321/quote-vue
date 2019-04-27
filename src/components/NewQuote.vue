<template>
    <div class="row">
        <form>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <label>Quote</label>            
                <textarea class="form-control" rows="3" v-model="quote" v-on:keyup="enter"></textarea>
            </div>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
            </div>

        </form>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                quote: ''
            }
        },
        methods: {
            createNew() {
                this.$emit('quoteAdded', this.quote);
                this.quote = '';
            },
            enter(e) {
                 if (e.keyCode === 13) {
                     this.createNew();
                 }
            }
        }
    }
</script>

<style scoped>

</style>


