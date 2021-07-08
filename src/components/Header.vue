<template>
    <header class="bg-dark">
        <div class="container-lg">
            <div class="col-2 py-3">
                <img src="@/img/spotify-logo.png" alt="">
            </div>
        </div>
    </header>
</template>

<script>
export default {
    name: "Header",
}
</script>

<style scoped lang="scss">
    header{
        .container-lg{
            .col-2{
                img{
                    height: 50px;
                    width: 50px;
                }
            }
        }
    }
</style>