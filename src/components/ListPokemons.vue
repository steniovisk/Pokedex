<script setup>
const pokemon = defineProps(["name","url"])


</script>

<template>
    <div class="col-4">
        <div class="card mb-3">
            <p class="text-center">{{pokemon.name}}</p>
            <div class="card" style="width: 11rem;">
  <img class="card-img-top" src="https://th.bing.com/th/id/R.f765e94181fac9bca7a51a8e21954352?rik=t3N22QDRGu3S%2fw&riu=http%3a%2f%2ffc00.deviantart.net%2ffs71%2fi%2f2012%2f242%2f4%2fe%2f21__spearow__vector__by_inkomingvirus-d5cy2ob.png&ehk=rX5Nl4JxW%2fS%2fcGqhU9HVVe%2b860JNsRRBhw5j%2fvUBR4g%3d&risl=&pid=ImgRaw&r=0" alt="Card image cap">
  <div class="card-body">
    <h5 class="card-title">{{pokemon.name}}</h5>
    <p class="card-text">Sobre o pokemon</p>
    <a :href="pokemon.url" class="btn btn-info col-12">Selecionar</a>
  </div>
</div>
        </div>
    
    </div>
</template>

<style>

</style>