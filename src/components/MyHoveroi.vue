<template>
    <div class="container">
        <div class="row">
            <div v-b-hover="handleHover1" class="col border rounded py-3 px-4">
                <b-icon v-if="isHovered" icon="battery-full" scale="4" variant="success"></b-icon>
                <b-icon v-else icon="battery" scale="2" ></b-icon>
                <span class="ml-2" :class="isHovered ? 'text-danger' : ''"></span>
            </div>
            <div  v-b-hover="handleHover2" class="col border rounded py-3 px-4">
                <b-icon v-if="isHovered" icon="bell-fill" scale="2" variant="danger"></b-icon>
                <b-icon v-else icon="bell" scale="2"></b-icon>
                <span class="ml-2" :class="isHovered ? 'text-danger' : ''"></span>
            </div>
            <div v-b-hover="handleHover3" class="col border rounded py-3 px-4">
                <b-icon v-if="isHovered" icon="briefcase-fill" scale="2" variant="primary"></b-icon>
                <b-icon v-else icon="briefcase" scale="2"></b-icon>
                <span class="ml-2" :class="isHovered ? 'text-danger' : ''"></span>
            </div>
            <div class="row col">
                <b-button-group>
                    <b-button variant="outline-primary">
                    <b-icon icon="person-fill"></b-icon> Account
                    </b-button>
                    <b-button variant="outline-primary">
                    <b-icon icon="tools"></b-icon> Settings<b-badge variant="light">4</b-badge>
                    </b-button>
                    <b-button variant="outline-primary">
                    <b-icon icon="inbox-fill"></b-icon> Messages<b-badge variant="success">32</b-badge>
                    </b-button>
                    <b-button variant="outline-primary">
                    <b-icon icon="briefcase-fill"></b-icon> Files<b-badge variant="danger">147</b-badge>
                    </b-button>
                </b-button-group>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Hoveroi.vue",
        data() {
      return {
        isHovered: false
      }
    },
    methods: {
        handleHover1(hovered) {
        this.isHovered = hovered
            },
        handleHover2(hovered) {
        this.isHovered = hovered
      },
        handleHover3(hovered) {
        this.isHovered = hovered
      }
    }
    }
</script>

<style scoped>

</style>