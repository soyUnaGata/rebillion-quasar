<template>
    <div class="country-dropdown">
        <button v-if="currentValue" type="button" class="country-dropdow-btn" @click.stop="show = !show">
            <img class="country-dropdown-img" :src="currentValue.icon" alt="">
            <span v-text="currentValue.phoneCode"></span>
            <img class="country-dropdown-img country-dropdown-arrow" v-if="show" src="../assets/arrow-small-up.svg" />
            <img class="country-dropdown-img country-dropdown-arrow" v-else src="../assets/arrow-small-down.svg" />
        </button>
        <div v-else class="country-dropdow-btn" @click.stop="show = !show">
            <div style="width: 20px;"></div>
            <div style="width: 20px;"></div>
            <img class="country-dropdown-img country-dropdown-arrow" v-if="show" src="../assets/arrow-small-up.svg" />
            <img class="country-dropdown-img country-dropdown-arrow" v-else src="../assets/arrow-small-down.svg" />
        </div>
        <Transition>
            <div class="country-dropdown-menu" v-if="show">
                <div class="country-dropdown-item" v-for="option in formatedOptions" @click.stop="select(option)">
                    <img class="country-dropdown-img" :src="option.icon" alt="">
                    <span v-text="option.phoneCode"></span>
                </div>
            </div>
        </Transition>
    </div>
</template>

<script>
    import { defineComponent } from 'vue'

    export default defineComponent({
        props:{
            modelValue: {
                type: String,
                required: true
            }
        },
        emits: ['update:modelValue'],
        name: 'PhoneCountryCodeSelect',
        data(){
            return {
                options: [
                    { countryCode: "US", phoneCode: "+1" },
                    { countryCode: "CA", phoneCode: "+1" },
                    { countryCode: "MX", phoneCode: "+52" },
                    { countryCode: "AR", phoneCode: "+54" },
                    { countryCode: "BR", phoneCode: "+55" },
                    { countryCode: "CL", phoneCode: "+56" },
                    { countryCode: "CO", phoneCode: "+57" },
                    { countryCode: "EC", phoneCode: "+593" },
                    { countryCode: "PE", phoneCode: "+51" },
                    { countryCode: "VE", phoneCode: "+58" },
                    { countryCode: "AU", phoneCode: "+61" },
                    { countryCode: "CN", phoneCode: "+86" },
                    { countryCode: "IN", phoneCode: "+91" },
                    { countryCode: "JP", phoneCode: "+81" },
                    { countryCode: "KR", phoneCode: "+82" },
                    { countryCode: "MY", phoneCode: "+60" },
                    { countryCode: "NZ", phoneCode: "+64" },
                    { countryCode: "PH", phoneCode: "+63" },
                    { countryCode: "SG", phoneCode: "+65" },
                    { countryCode: "TH", phoneCode: "+66" },
                    { countryCode: "TW", phoneCode: "+886" },
                    { countryCode: "VN", phoneCode: "+84" },
                ],
                show: false
            }
        },
        computed:{
            formatedOptions() {
                return this.options.map(option => (Object.assign({}, option, { icon: `/img/flags/${option.countryCode}.svg` })))
            },
            currentValue: {
                get(){
                    return this.modelValue;
                },
                set(val){
                    this.$emit('update:modelValue', val)
                }
            }
        },
        methods:{
            select(option){
                this.currentValue = option;
                this.show = false;
            },
            hide(){
                this.show = false;
            }
        },
        mounted(){
            window.addEventListener('click', this.hide)
        },
        unmounted(){
            window.removeEventListener('click', this.hide);
        }
    })
</script>

<style scoped>
    .country-dropdow{
        position: relative;
    }

    .country-dropdow-btn{
        padding: 15px 16px;
        display: flex;
        gap: 10px;
        background-color: var(--bg--cart);
        border-radius: 100px 0px 0px 100px;
        outline: none;
        border: none;
    }
    .country-dropdow-btn--empty{
        width: 127px;
        height: 50px;
    }
    .country-dropdown-img{
        height: 20px;
        width: 20px;
    }

    .country-dropdown-item{
        padding: 15px 16px;
        display: flex;
        gap: 10px;    
        background-color: var(--bg--shipping);
        cursor: pointer;
    }

    .country-dropdown-menu{
        display: flex;
        flex-direction: column;
        position: absolute;
        top: calc(100% + 4px);
        left: 0;
        background-color: var(--bg--shipping);
        z-index: 99;
        max-height: 200px;
        overflow: auto;
    }
</style>