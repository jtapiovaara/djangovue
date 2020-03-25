<template>
    <div class="container">
            <b-col md="auto">
                <b-form-group label="Select calendar interactive state">
                    <b-form-radio-group v-model="state" aria-controls="ex-disabled-readonly">
                        <b-form-radio value="disabled">Disabled</b-form-radio>
                        <b-form-radio value="readonly">Readonly</b-form-radio>
                        <b-form-radio value="normal">Normal</b-form-radio>
                    </b-form-radio-group>
                </b-form-group>
                <b-calendar
                        class="border rounded p-2"
                        v-model="value"
                        @context="onContext"
                        block
                        id="ex-disabled-readonly"
                        locale="fi"
                        selected-variant="success"
                        today-variant="primary"
                        :date-disabled-fn="dateDisabled"
                        :date-info-fn="dateClass"
                        :disabled="disabled"
                        :readonly="readonly"
                        :max="max"
                        :min="min"
                ></b-calendar>
            </b-col>
        <br>
            <b-col class="col">
                <p>Valittuna: <b>'{{ value }}'</b></p>
                <p class="mb-0">Context:</p>
                <pre class="small">{{ context }}</pre>
            </b-col>
    </div>
</template>

<script>
    export default {
        name: "Kalenteri",
        data() {
            const now = new Date()
            const today = new Date(now.getFullYear(), now.getMonth(), now.getDate())
            // 15th two months prior
            const minDate = new Date(today)
            minDate.setMonth(minDate.getMonth() - 2)
            minDate.setDate(15)
            // 15th in two months
            const maxDate = new Date(today)
            maxDate.setMonth(maxDate.getMonth() + 2)
            maxDate.setDate(15)
            return {
                value: '',
                min: minDate,
                max: maxDate,
                context: null,
                state: 'disabled'
            }
        },
        computed: {
            disabled() {
                return this.state === 'disabled'
            },
            readonly() {
                return this.state === 'readonly'
            }
        },
        methods: {
            onContext(ctx) {
                this.context = ctx
            },
            dateDisabled(ymd, date) {
                // Disable weekends (Sunday = `0`, Saturday = `6`) and
                // disable days that fall on the 13th of the month
                const weekday = date.getDay()
                const day = date.getDate()
                // Return `true` if the date should be disabled
                return weekday === 0 || weekday === 6 || day === 13
            },
            dateClass(ymd, date) {
                const day = date.getDate()
                return day > 5 && day < 7 ? 'table-info' : 'Birthday!'
            }

        }
    }
</script>

<style scoped>

</style>