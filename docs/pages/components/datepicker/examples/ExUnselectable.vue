<template>
    <section>
        <b-field grouped group-multiline>
            <b-field>
                <b-switch v-model="unselectableWeekends">Unselectable weekends</b-switch>
            </b-field>
            <b-field label="Unselectable day of month">
                <b-input type="number" min="1" max="31" v-model.number="unselectableDayOfMonth" />
            </b-field>
        </b-field>
        <b-datepicker v-model="date"
            inline
            :unselectable-days-of-week="unselectableWeekends ? [0, 6] : null"
            :unselectable-days-of-month="[unselectableDayOfMonth]">
        </b-datepicker>
    </section>
</template>

<script>
    export default {
        data() {
            return {
                date: new Date(),
                unselectableWeekends: true,
                unselectableDayOfMonth: 1
            }
        }
    }
</script>
