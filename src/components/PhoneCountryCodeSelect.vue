<template>
    <q-btn-dropdown push>
       <template v-slot:label>
        <div class="country-dropdown">
            <img class="country-dropdown-img" :src="selected.icon" alt="">
            <span v-text="selected.phoneCode"></span>
            <img class="country-dropdown-img country-dropdown-arrow" src="../assets/arrow-small-down.svg" />
        </div>
      </template>
      <q-list>  
        <q-item clickable v-close-popup @click="onItemClick">
          <q-item-section>
            <q-item-label>Photos</q-item-label>
          </q-item-section>
        </q-item>

        <q-item clickable v-close-popup @click="onItemClick">
          <q-item-section>
            <q-item-label>Videos</q-item-label>
          </q-item-section>
        </q-item>

        <q-item clickable v-close-popup @click="onItemClick">
          <q-item-section>
            <q-item-label>Articles</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-btn-dropdown>
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
                codes: [
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
                selected: null
            }
        },
        computed:{
            codesWithImages() {
                return this.codes.map(code => (Object.assign({}, code, { icon: `/img/flags/${code.countryCode}.svg` })))
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
        created(){
            this.selected = this.codesWithImages[0];
        }
    })
</script>

<style scoped>
    .country-dropdown{
        padding: 15px 16px;
        display: flex;
        gap: 10px;
        background-color: var(--bg--cart);
        border-radius: 100px 0px 0px 100px;
    }
    .country-dropdown-img{
        height: 20px;
        width: 20px;
    }

    .country-dropdown-item{
        padding: 15px 16px;
        display: flex;
        gap: 10px;    
    }
    body.desktop .q-focusable:focus > .q-focus-helper, body.desktop .q-manual-focusable--focused > .q-focus-helper, body.desktop .q-hoverable:hover > .q-focus-helper {
        background: none;
        opacity: 0.15; 
    }
    body.desktop .q-focus-helper:before {
        background: none;
    }
    .q-btn-dropdown--simple * + .q-btn-dropdown__arrow {
        margin-left: none;
        display: none;
    }
    .q-btn--push {
        border-radius: none;
    }
    .q-btn--push {
        border-radius: 100px 0px 0px 100px;
        border: none;
    }
    .q-btn{
        padding: none;
    }
    .q-btn:before {
    content: "";
    display: block;
    position: absolute;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
    border-radius: none;
    box-shadow: none;
}
</style>