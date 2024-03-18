<template class="container">
  <h1 class="h1">{{ msg }}</h1>
  <div class="">
    <div class="col-12">
      <textarea ref="showNumber" v-model="showNumber" class="form-control col-10 text-primary"
                style="font-size: 7rem!important" rows="1" disabled></textarea>
      <button @click="discovery" class="btn btn-success btn-sm mt-2 me-2"><i class="bi bi-plus-lg"></i> Descubrir
      </button>
      <button @click="retro" class="btn btn-primary btn-sm mt-2">- Devolver</button>
      <hr>
      <button @click="reset" class="btn btn-danger btn-sm"><i class="bi bi-arrow-clockwise"></i> Reiniciar</button>
    </div>
    <div class="col-12 row">
      <div style="margin-top: 4rem" class="col-6 text-end fs-1 text-success">Cifras de Pí:</div>
      <div style="font-size: 7rem!important" class="col-6 text-start fs-1 text-success fw-bold">{{countWords}}</div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'ChallengePi',
  props: {
    msg: String
  },
  data: () => {
    return {
      countWords: 0,
      pi: "3.141592653589793238462643383279502884197169399375105820974944592307816406286208998628034825342117067982148086513282306647093844609550582231725359408128481117450284102701938521105559644622948954930381964428810975665933446128475648233786783165271201909145648566923460348610454326648213393607260249141273724587006606315588174881520920962829254091715364367892590360011330530548820466521384146951941511609433057270365759591953092186117381932611793105118548074462379962749567351885752724891227938183011949129833673362440656643086021394946395224737190702179860943702770539217176293176752384674818467669405132000568127145263560827785771342757789609173637178721468440901224953430146549585371050792279689258923542019956112129021960864034418159813629774771309960518707211349999998372978049951059731732816096318595024459455346908302642522308253344685035261931188171010003137838752886587533208381420617177669147303598253490428755468731159562863882353787593751957781857780532171226806613001927876611195909216420198",
      competitors: []
    }
  },
  methods: {
    discovery() {
      this.countWords++
      //console.log(this.$refs)
    },
    retro() {
      if (this.countWords > 0) {
        this.countWords--
      }
    },
    reset() {
      this.countWords = 0
    }
  },
  watch: {
    showNumber: function () {
      let textarea = this.$refs.showNumber
      setTimeout(()=>{
        textarea.scrollTop = textarea.scrollHeight
      },2)
    }
  },
  computed: {
    showNumber() {
      return "3." + this.pi.substring(2, this.countWords + 2)
    }
  }

}
</script>

<style scoped>
.countWord {
  color: darkgreen;
  font-weight: bold;
  font-size: 20px;
}
</style>