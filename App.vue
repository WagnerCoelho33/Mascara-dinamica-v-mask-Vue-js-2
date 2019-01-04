<template>
  <div class="wrapper h-100">
    <div class="container">
      <section class="header">
        <h2 class="header">
          Exemplo simples de mascara dinâmica para o Vue.js
        </h2>
      </section>

      <section class="special-examples">
        <h4 class="header">Mascara dinâmica</h4>
        <div class="row">
          <div class="six columns">
            <label>
              <input
                type="radio"
                id="cpf-example"
                value="###.###.###-##"
                v-model="dynamicMask"
              />
              <span class="label-body">Pessoa Física</span>
            </label>

            <label>
              <input
                type="radio"
                id="cnpj-example"
                value="##.###.###/####-##"
                v-model="dynamicMask"
              />
              <span class="label-body">Pessoa Jurídica</span>
            </label>
          </div>
          <div class="six columns">
            <label if="cnpj-example" for="time-and-date-ex">CPF / CNPJ</label>
            <input
              type="text"
              class="u-full-width"
              v-mask="dynamicMask"
              :placeholder="dynamicMask"
              v-model="models.dynamicMask"
            />
          </div>
        </div>
      </section>

      <section class="examples">
        <div class="row">
          <div class="six columns">
            <label for="time-and-date-ex">Data e Hora</label>
          </div>
          <div class="six columns">
            <input
              class="u-full-width"
              id="time-and-date-ex"
              type="text"
              placeholder="27/10/2016 23:15"
              v-mask="'##/##/#### ##:##'"
              v-model="models.timeAndDate"
            />
          </div>
        </div>

        <div class="row">
          <div class="six columns">
            <label for="time-ex">Hora e segundos</label>
          </div>
          <div class="six columns">
            <input
              class="u-full-width"
              id="time-ex"
              type="text"
              placeholder="11:23:15"
              v-mask="'##:##:##'"
              v-model="models.timeWithSeconds"
            />
          </div>
        </div>

        <div class="row">
          <div class="six columns">
            <label for="credit-cart-ex">Cartão de Crédito</label>
          </div>
          <div class="six columns">
            <input
              class="u-full-width"
              id="credit-cart-ex"
              type="text"
              placeholder="4444 4444 4444 4444"
              v-mask="'#### #### #### ####'"
              v-model="models.cardNumber"
            />
          </div>
        </div>

        <div class="row">
          <div class="six columns">
            <label for="credit-cart-ex">Telefone Fixo</label>
          </div>
          <div class="six columns">
            <input
              class="u-full-width"
              id="phone-number-ex"
              type="text"
              placeholder="(99) 9999-9999"
              v-mask="'(##) 9###-####'"
              v-model="models.phoneNumber"
            />
          </div>
        </div>

        <div class="row">
          <div class="six columns">
            <label for="credit-cart-ex">Telefone Celular</label>
          </div>
          <div class="six columns">
            <input
              class="u-full-width"
              id="us-phone-number-ex"
              type="text"
              placeholder="(99) 9 9999-9999"
              v-mask="'(##) # ####-####'"
              v-model="models.brPhoneNumber"
            />
          </div>
        </div>

        <div class="row">
          <div class="six columns">
            <label for="credit-cart-ex">US Phone Number</label>
          </div>
          <div class="six columns">
            <input
              class="u-full-width"
              id="us-phone-number-ex"
              type="text"
              placeholder="+1(999)-999-9999"
              v-mask="'+1(###)-###-####'"
              v-model="models.usPhoneNumber"
            />
          </div>
        </div>
      </section>

      <section class="footer">
        <a href="" class="button button-primary">Salvar</a>
      </section>
    </div>
  </div>
</template>
<script>
export default {
  name: "Demo",
  data() {
    return {
      dynamicMask: "###.###.###-###",
      models: {
        timeAndDate: "",
        timeWithSeconds: "",
        cardNumber: "",
        phoneNumber: "",
        dynamicMask: "",
        usPhoneNumber: "",
        brPhoneNumber: ""
      }
    };
  }
};
</script>
<style lang="scss">
body,
html {
  height: 100%;
  min-height: 100%;
}
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}
.h-100 {
  height: 100%;
}
section.header {
  margin-bottom: 4rem;
  text-align: center;
}
section.footer {
  margin-top: 3.5rem;
  text-align: center;
}

section.special-examples {
  margin-top: 4rem;
}
section.special-examples h4 {
  text-align: center;
}
</style>
