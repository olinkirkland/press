<template>
    <footer class="w-full flex justify-center py-10">
        <div class="max-w-page flex justify-between gap-3">
            <div class="max-w-md flex flex-col gap-3 items-start">
                <img
                    class="h-15 mb-4"
                    src="../assets/images/logo/logo-on-light.png"
                    alt="Kirkland Press logo"
                />
                <p>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Eveniet corporis sequi
                    tempora voluptatem repellat libero veniam modi obcaecati ad eius.
                </p>
                <p>
                    <a href="">https://www.olinkirk.land</a> |
                    <a href="mailto:hello@kirkland.press">hello@kirkland.press</a>
                </p>
            </div>
        </div>
    </footer>
</template>

<style lang="scss" scoped>
footer {
    background-color: $pale-gray;
    color: $black;
    > * {
        opacity: 0.75;
    }
}
</style>
