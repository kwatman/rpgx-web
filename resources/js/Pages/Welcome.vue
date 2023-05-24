<script setup>
import { Head, Link } from '@inertiajs/vue3';

defineProps({
    canLogin: {
        type: Boolean,
    },
    canRegister: {
        type: Boolean,
    },
    laravelVersion: {
        type: String,
        required: true,
    },
    phpVersion: {
        type: String,
        required: true,
    },
});
</script>

<template>
    <Head title="Welcome" />

    <div
        class=""
    >
        <div v-if="canLogin" class="">
            <Link
                v-if="$page.props.auth.user"
                :href="route('dashboard')"
                class=""
                >Dashboard</Link
            >

            <template v-else>
                <Link
                    :href="route('login')"
                    class=""
                    >Log in</Link
                >

                <Link
                    v-if="canRegister"
                    :href="route('register')"
                    class=""
                    >Register</Link
                >
            </template>
        </div>

    </div>
</template>

<style>

</style>
