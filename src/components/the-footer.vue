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
                <div class="flex gap-5">
                    <a href="">
                        <img src="../assets/icons/black/link.png" />
                        www.olinkirk.land
                    </a>
                    |
                    <a href="mailto:press@olinkirk.land">
                        <img src="../assets/icons/black/mail.png" />
                        press@olinkirk.land
                    </a>
                </div>
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
