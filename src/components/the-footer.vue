<template>
    <footer class="w-full flex justify-center">
        <div class="flex max-w-page py-10">
            <div class="flex-1">
                <img
                    class="h-20 mb-4 opacity-75"
                    src="../assets/images/logo/logo-on-dark.png"
                    alt="Kirkland Press logo"
                />
                <p class="max-w-lg mb-2">
                    I make independent tabletop roleplaying games and other writing. I also make
                    websites, apps, and other digital things.
                </p>
                <p>
                    <a href="https://olinkirk.land/" target="_blank" rel="noopener noreferrer"
                        >Visit my personal site</a
                    >
                </p>
            </div>

            <div class="grid grid-cols-2">
                <div>
                    <h4 class="mb-2">Explore</h4>
                    <ul class="flex flex-col gap-1">
                        <li><a href="#">Home</a></li>
                        <li><a href="#">About</a></li>
                        <li><a href="#">Collection</a></li>
                    </ul>
                </div>

                <div>
                    <h4 class="mb-2">Contact</h4>
                    <ul class="flex flex-col gap-1">
                        <li>
                            <a href="mailto:hello@kirklandpress.com">hello@kirklandpress.com</a>
                        </li>
                        <li><a href="#">itch.io</a></li>
                        <li><a href="#">Follow along</a></li>
                    </ul>
                </div>
            </div>
        </div>
    </footer>
</template>

<style lang="scss" scoped>
footer {
    background-color: $black;
    color: $white;
}
</style>
