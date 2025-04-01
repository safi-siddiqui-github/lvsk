<script setup lang="ts">
import NormalButton from '@/components/button/NormalButton.vue';
import NormalLink from '@/components/link/NormalLink.vue';
import { Menu, Search } from 'lucide-vue-next';

const toggleOpenMenu = () => {
    console.log('haah');
};

const navMenu = [
    {
        title: 'Search',
        href: route('dashboard'),
        // icon: <Search class="size-5" />,
    },
    {
        title: 'Cart',
        href: route('dashboard'),
        // icon: <ShoppingBag class="size-5" />,
    },
    {
        title: 'Products',
        href: route('dashboard'),
        // icon: <ShoppingCart class="size-5" />,
    },
    {
        title: 'Categories',
        href: route('dashboard'),
        // icon: <ChartBarStacked class="size-5" />,
    },
    {
        title: 'Orders',
        href: route('dashboard'),
        // icon: <Archive class="size-5" />,
    },
];
</script>

<template>
    <div class="relative">
        <header class="flex items-center justify-between border-b border-slate-500 px-2 py-1 sm:px-4 sm:py-2 sm:pr-6">
            <NormalLink :href="route('home')" addClasses="text-lg tracking-tight">LVSK</NormalLink>

            <nav class="flex items-center">
                <NormalButton addClasses="active:outline active:rounded sm:hidden" @click="toggleOpenMenu">
                    <Menu class="size-5" />
                </NormalButton>
            </nav>

            <nav class="hidden items-center gap-2 sm:flex">
                <nav class="hidden sm:flex">
                    <NormalLink
                        v-for="(navItem, index) in navMenu"
                        :href="navItem.href"
                        addClasses="flex items-center gap-2 hover:outline active:outline rounded"
                        :key="`NavMenu-${index}`"
                    >
                        {{ icon }}
                        <p class="hidden md:inline-block">{{ navItem.title }}</p>
                    </NormalLink>

                </nav>

                <!-- <MainToggleAppearance /> -->

                <!-- <div class={cn('', { hidden: auth?.user, flex: !auth?.user, })}>
                    <PrimaryLink href={route('login')}>Login</PrimaryLink>
                </div> -->

                <!-- <div class={cn('', { hidden: !auth?.user, flex: auth?.user, })}>
                    <PrimaryLogout />
                </div> -->
            </nav>
        </header>

        <!-- <section class={cn('absolute top-0 right-0 flex h-screen justify-end overflow-hidden bg-black/10 sm:hidden',
            { 'w-0' : openMenu==false, 'w-full' : openMenu==true, })}>
            <div class={cn( 'animate-in flex h-screen flex-col overflow-hidden border-l border-slate-500 bg-white delay-100 duration-100 dark:bg-black'
                , { 'slide-in-from-left w-0' : openMenu==false, 'slide-in-from-right w-full max-w-72' : openMenu==true,
                }, )}>
                <div class="flex items-center justify-between border-b border-slate-500 p-2">
                    <MainToggleAppearance />

                    <NormalButton addClasses="active:outline active:rounded" onClick={toggleOpenMenu}>
                        <CircleX class="size-5" />
                    </NormalButton>
                </div>

                <div class="flex flex-col gap-6 p-2">
                    <nav class="flex flex-col gap-4">
                        <EmphasizeText>LRSVES Menu</EmphasizeText>

                        <div class="flex flex-col gap-1">
                            {navMenu.map(({ title, href, icon }, index) => (
                            <NormalLink key={`NavMenu-${index}`} href={href}
                                addClasses="flex items-center gap-2 text-lg">
                                {icon}
                                {title}
                            </NormalLink>
                            ))}
                        </div>
                    </nav>

                    <div class="flex flex-col items-center gap-2">
                        <EmphasizeText>LRSVES Members</EmphasizeText>
                        <p class={cn('text-center', { hidden: auth?.user, flex: !auth?.user, })}>
                            Join and become our member at LRSVES. Sign in with your account to have exclusive deals and
                            much more.
                        </p>
                        <div class={cn('flex-wrap items-center gap-2', { hidden: auth?.user, flex: !auth?.user, })}>
                            <PrimaryLink href={route('login')}>Login</PrimaryLink>
                            <SecondaryLink href={route('home')}>Register</SecondaryLink>
                        </div>
                        <p class={cn('text-center', { hidden: !auth?.user, flex: auth?.user, })}>
                            Welcome {auth?.user?.name ?? 'User'}
                        </p>

                        <div class={cn('', { hidden: !auth?.user, flex: auth?.user, })}>
                            <PrimaryLogout />
                        </div>
                    </div>
                </div>
            </div>
        </section> -->
    </div>
</template>
