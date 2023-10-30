<template>
  <br>
  <div class="container">
    <div class="row">
      <div class="col text-center">
        <h1 class="text-with-shadown"> {{traslate('title')}}</h1>
      </div>
    </div>



    <div class="row mt-4">
      <div class="col-md-4">
        <button class="btn btn-with-background" @click="calcular()">{{traslate('calcular')}}</button>
        <div class="d-flex bd-highlight ">
          <div class="p-2 bd-highlight text-with-shadown">{{traslate('calcularRecursos')}}</div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" :value="calcular_recursos" v-model="calcular_recursos" @change="onChangeRecursos($event)" role="switch">
            </div>
          </div>
        </div>
      </div>
      <div class="col">
        <a class="btn btn-with-background" href="https://stream.hivelive.me/donate/misticogama"
           style="color: #7205ee; text-decoration: none;" target="_blank">{{traslate('donacion')}}</a>
      </div>
      <div class="col-md-3 ms-auto">
        <div class="form-floating">
          <select class="form-select" id="floatingSelect" aria-label="Floating label select example"
              v-model="idioma" >
            <option value="ES" selected>Spanish</option>
            <option value="EN">English</option>
          </select>
          <label for="floatingSelect">{{traslate('lenguaje')}}</label>
        </div>
      </div>
    </div>


    <h5 class="text-with-shadown">{{traslate('estadisticas')}} <button class="btn btn-with-background-small" @click="alerta(traslate('estadisticas'),traslate('infoStadistica'))">?</button></h5>
    <div class="row  text-with-shadown">
      <div class="col">
        <RecursoComponent :src="'assets/energia.png'"
                          :width="7"
                          :cantidad="total_energia"></RecursoComponent>
        <RecursoComponent :src="'assets/agua.png'"
                          :width="10"
                          :cantidad="total_agua"></RecursoComponent>
        <RecursoComponent :src="'assets/madera.png'"
                          :width="10"
                          :cantidad="total_madera"></RecursoComponent>
        <RecursoComponent :src="'assets/carbon.png'"
                          :width="10"
                          :cantidad="total_carbon"></RecursoComponent>
      </div>
      <div class="col">
        <RecursoComponent :src="'assets/maiz.png'"
                          :width="7"
                          :cantidad="total_maiz"></RecursoComponent>
        <RecursoComponent :src="'assets/trigo.png'"
                          :width="7"
                          :cantidad="total_trigo"></RecursoComponent>
        <RecursoComponent :src="'assets/bolsa_maiz.png'"
                          :width="8.9"
                          :cantidad="total_bolsa_maiz"></RecursoComponent>
        <RecursoComponent :src="'assets/bolsa_trigo.png'"
                          :width="8"
                          :cantidad="total_bolsa_trigo"></RecursoComponent>
      </div>
      <div class="col">
        <RecursoComponent :src="'assets/leche.png'"
                          :width="10"
                          :cantidad="total_leche"></RecursoComponent>
        <RecursoComponent :src="'assets/huevo.png'"
                          :width="10"
                          :cantidad="total_huevo"></RecursoComponent>
        <RecursoComponent :src="'assets/kod.png'"
                          :width="7"
                          :cantidad="total_kod"></RecursoComponent>
        <RecursoComponent :src="'assets/hueso.png'"
                          :width="7"
                          :cantidad="total_hueso"></RecursoComponent>
      </div>
    </div>

    <div class="row  text-with-shadown">
      <div class="col">
        <p>

          <button class="btn btn-with-background" data-bs-toggle="collapse" href="#collapseDatosIniciales" role="button"
                  aria-expanded="false"
                  aria-controls="collapseExample">
            {{traslate('ingresarRecursos')}}
          </button>
          <button class="btn btn-with-background-small" @click="alerta(traslate('ingresarRecursos'),traslate('infoIngresarRecursos'))">?</button>
          <button class="btn btn-with-background" data-bs-toggle="collapse" href="#collapseExample" role="button"
                  aria-expanded="false"
                  aria-controls="collapseExample">
            {{traslate('produccionTotal')}}
          </button>
          <button class="btn btn-with-background-small" @click="alerta(traslate('produccionTotal'),traslate('infoProduccionTotal'))">?</button>
        <button class="btn btn-with-background" data-bs-toggle="collapse" href="#collapseObtenido" role="button"
                  aria-expanded="false"
                  aria-controls="collapseExample">
            {{traslate('obtencionIndividual')}}
          </button>
          <button class="btn btn-with-background-small" @click="alerta(traslate('obtencionIndividual'),traslate('infoObtencionIndividual'))">?</button>
        </p>
        <div class="collapse caja-cafe" id="collapseDatosIniciales">
          <div class="card card-body relleno-cafe">
            <div class="row">
              <div class="col">

                <div class="row">
                  <div class="col">

                    <div class="form-floating mb-3">
                      <input type="number" v-model="inicial_energia"
                             class="form-control" id="floatingInput"
                             placeholder="name@example.com">
                      <label for="floatingInput"><img  :src="'assets/energia.png'"  v-bind:style="{'height':'100%'}" alt="" ></label>
                    </div>

                    <div class="form-floating mb-3">
                      <input type="number"  v-model="inicial_agua"
                             class="form-control" id="floatingInput"
                             placeholder="name@example.com">
                      <label for="floatingInput"><img  :src="'assets/agua.png'"  v-bind:style="{'height':'100%'}" alt="" ></label>
                    </div>

                    <div class="form-floating mb-3">
                      <input type="number" v-model="inicial_madera"
                             class="form-control" id="floatingInput"
                             placeholder="name@example.com">
                      <label for="floatingInput"><img  :src="'assets/madera.png'"  v-bind:style="{'height':'100%'}" alt="" ></label>
                    </div>

                    <div class="form-floating mb-3">
                      <input type="number" v-model="inicial_carbon"
                             class="form-control" id="floatingInput"
                             placeholder="name@example.com">
                      <label for="floatingInput"><img  :src="'assets/carbon.png'"  v-bind:style="{'height':'100%'}" alt="" ></label>
                    </div>


                  </div>
                  <div class="col">

                    <div class="form-floating mb-3">
                      <input type="number" v-model="inicial_maiz"
                             class="form-control" id="floatingInput"
                             placeholder="name@example.com">
                      <label for="floatingInput"><img  :src="'assets/maiz.png'"  v-bind:style="{'height':'100%'}" alt="" ></label>
                    </div>

                    <div class="form-floating mb-3">
                      <input type="number" v-model="inicial_trigo"
                             class="form-control" id="floatingInput"
                             placeholder="name@example.com">
                      <label for="floatingInput"><img  :src="'assets/trigo.png'"  v-bind:style="{'height':'100%'}" alt="" ></label>
                    </div>

                    <div class="form-floating mb-3">
                      <input type="number" v-model="inicial_bolsa_maiz"
                             class="form-control" id="floatingInput"
                             placeholder="name@example.com">
                      <label for="floatingInput"><img  :src="'assets/bolsa_maiz.png'"  v-bind:style="{'height':'100%'}" alt="" ></label>
                    </div>

                    <div class="form-floating mb-3">
                      <input type="number" v-model="inicial_bolsa_trigo"
                             class="form-control" id="floatingInput"
                             placeholder="name@example.com">
                      <label for="floatingInput"><img  :src="'assets/bolsa_trigo.png'"  v-bind:style="{'height':'100%'}" alt="" ></label>
                    </div>

                  </div>
                  <div class="col">

                    <div class="form-floating mb-3">
                      <input type="number" v-model="inicial_semilla_trigo"
                             class="form-control" id="floatingInput"
                             placeholder="name@example.com">
                      <label for="floatingInput"><img  :src="'assets/semilla_trigo.png'"  v-bind:style="{'height':'100%'}" alt="" ></label>
                    </div>
                    <div class="form-floating mb-3">
                      <input type="number" v-model="inicial_semilla_maiz"
                             class="form-control" id="floatingInput"
                             placeholder="name@example.com">
                      <label for="floatingInput"><img  :src="'assets/semilla_maiz.png'"  v-bind:style="{'height':'100%'}" alt="" ></label>
                    </div>
                    <div class="form-floating mb-3">
                      <input type="number" v-model="inicial_leche"
                             class="form-control" id="floatingInput"
                             placeholder="name@example.com">
                      <label for="floatingInput"><img  :src="'assets/leche.png'"  v-bind:style="{'height':'100%'}" alt="" ></label>
                    </div>
                    <div class="form-floating mb-3">
                      <input type="number" v-model="inicial_huevo"
                             class="form-control" id="floatingInput"
                             placeholder="name@example.com">
                      <label for="floatingInput"><img  :src="'assets/huevo.png'"  v-bind:style="{'height':'100%'}" alt="" ></label>
                    </div>

                  </div>
                </div>

              </div>

            </div>
          </div>
        </div>
        <div class="collapse caja-cafe" id="collapseExample">
          <div class="card card-body relleno-cafe">
            <div class="row">
              <div class="col">
                <h5>{{traslate('produccionTotal')}}</h5>
                <div class="row">
                  <div class="col">
                    <RecursoComponent :src="'assets/energia.png'"
                                      :width="10"
                                      :cantidad="total_energia"></RecursoComponent>
                    <RecursoComponent :src="'assets/agua.png'"
                                      :width="10"
                                      :cantidad="total_agua"></RecursoComponent>
                    <RecursoComponent :src="'assets/madera.png'"
                                      :width="10"
                                      :cantidad="total_madera"></RecursoComponent>
                    <RecursoComponent :src="'assets/carbon.png'"
                                      :width="10"
                                      :cantidad="total_carbon"></RecursoComponent>
                  </div>
                  <div class="col">
                    <RecursoComponent :src="'assets/maiz.png'"
                                      :width="10"
                                      :cantidad="total_maiz"></RecursoComponent>
                    <RecursoComponent :src="'assets/trigo.png'"
                                      :width="10"
                                      :cantidad="total_trigo"></RecursoComponent>
                    <RecursoComponent :src="'assets/bolsa_maiz.png'"
                                      :width="10"
                                      :cantidad="total_bolsa_maiz"></RecursoComponent>
                    <RecursoComponent :src="'assets/bolsa_trigo.png'"
                                      :width="10"
                                      :cantidad="total_bolsa_trigo"></RecursoComponent>
                  </div>
                  <div class="col">
                    <RecursoComponent :src="'assets/leche.png'"
                                      :width="10"
                                      :cantidad="total_leche"></RecursoComponent>
                    <RecursoComponent :src="'assets/huevo.png'"
                                      :width="10"
                                      :cantidad="total_huevo"></RecursoComponent>
                    <RecursoComponent :src="'assets/kod.png'"
                                      :width="10"
                                      :cantidad="total_kod"></RecursoComponent>
                    <RecursoComponent :src="'assets/hueso.png'"
                                      :width="10"
                                      :cantidad="total_hueso"></RecursoComponent>
                  </div>
                </div>

              </div>
              <div class="col">
                <h5>{{traslate('consumoTotal')}}</h5>
                <div class="row">
                  <div class="col">
                    <RecursoComponent :src="'assets/energia.png'"
                                      :width="10"
                                      :cantidad="consumo_energia"></RecursoComponent>
                    <RecursoComponent :src="'assets/agua.png'"
                                      :width="10"
                                      :cantidad="consumo_agua"></RecursoComponent>
                    <RecursoComponent :src="'assets/madera.png'"
                                      :width="10"
                                      :cantidad="consumo_madera"></RecursoComponent>
                    <RecursoComponent :src="'assets/carbon.png'"
                                      :width="10"
                                      :cantidad="consumo_carbon"></RecursoComponent>

                  </div>
                  <div class="col">
                    <RecursoComponent :src="'assets/maiz.png'"
                                      :width="10"
                                      :cantidad="consumo_maiz"></RecursoComponent>
                    <RecursoComponent :src="'assets/trigo.png'"
                                      :width="10"
                                      :cantidad="consumo_trigo"></RecursoComponent>
                    <RecursoComponent :src="'assets/bolsa_maiz.png'"
                                      :width="10"
                                      :cantidad="consumo_bolsa_trigo"></RecursoComponent>
                    <RecursoComponent :src="'assets/bolsa_trigo.png'"
                                      :width="10"
                                      :cantidad="consumo_bolsa_maiz"></RecursoComponent>
                  </div>
                  <div class="col">
                    <RecursoComponent :src="'assets/semilla_trigo.png'"
                                      :width="10"
                                      :cantidad="consumo_semilla_trigo"></RecursoComponent>
                    <RecursoComponent :src="'assets/semilla_maiz.png'"
                                      :width="10"
                                      :cantidad="consumo_semilla_maiz"></RecursoComponent>
                    <RecursoComponent :src="'assets/leche.png'"
                                      :width="10"
                                      :cantidad="consumo_leche"></RecursoComponent>
                    <RecursoComponent :src="'assets/huevo.png'"
                                      :width="10"
                                      :cantidad="consumo_huevo"></RecursoComponent>
                  </div>
                </div>

              </div>
            </div>
          </div>
        </div>
        <div class="collapse caja-cafe" id="collapseObtenido">
          <div class="card card-body relleno-cafe ">
            <div class="row">
              <h3> {{traslate('obtencionIndividual')}}</h3>

              <div class="row">
                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="traslate('pozoAgua')" :src-produccion="'assets/agua.png'"
                                             :titulo-consumo="traslate('consumo')"
                                             :titulo-produccion="traslate('produccion')"
                                             :src-consume="'assets/energia.png'" :produccion="produccion_agua"
                                             :consume2="0"
                                             :consume="requerimiento_energia_pozo"></ObtencionRecursoComponent>
                </div>
                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="traslate('fabricaEnegria')" :src-produccion="'assets/energia.png'"
                                             :titulo-consumo="traslate('consumo')"
                                             :titulo-produccion="traslate('produccion')"
                                             :src-consume="'assets/carbon.png'" :produccion="produccion_energia"
                                             :consume2="0"
                                             :consume="requerimiento_carbon_fabrica"></ObtencionRecursoComponent>
                </div>

                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="traslate('molinoLeche')" :src-produccion="'assets/kod.png'"
                                             :titulo-consumo="traslate('consumo')"
                                             :titulo-produccion="traslate('produccion')"
                                             :src-consume="'assets/leche.png'" :produccion="total_kod"
                                             :consume2="0"
                                             :consume="consumo_leche"></ObtencionRecursoComponent>
                </div>

                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="traslate('molinoHuevo')" :src-produccion="'assets/hueso.png'"
                                             :titulo-consumo="traslate('consumo')"
                                             :titulo-produccion="traslate('produccion')"
                                             :src-consume="'assets/huevo.png'" :produccion="total_hueso"
                                             :consume2="0"
                                             :consume="consumo_huevo"></ObtencionRecursoComponent>
                </div>

              </div>

              <div class="row">
                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="traslate('tierraTrigo')"
                                             :titulo-consumo="traslate('consumo')"
                                             :titulo-produccion="traslate('produccion')"
                                             :src-produccion="'assets/trigo.png'" :src-consume="'assets/agua.png'"
                                             :produccion=" produccion_trigo + produccion_trigo_2"
                                             :consume="requerimiento_agua_tierra_trigo + requerimiento_agua_tierra_trigo_2"
                                             :otro-rercuso="true"
                                             :consume2="requerimiento_semilla_trigo_tierra_trigo + requerimiento_semilla_trigo_tierra_trigo_2"
                                             :src-consume2="'assets/semilla_trigo.png'"></ObtencionRecursoComponent>
                </div>
                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="traslate('tierraMaiz')"
                                             :titulo-consumo="traslate('consumo')"
                                             :titulo-produccion="traslate('produccion')"
                                             :src-produccion="'assets/maiz.png'" :src-consume="'assets/agua.png'"
                                             :produccion="  produccion_maiz + produccion_maiz_2"
                                             :consume="requerimiento_agua_tierra_maiz + requerimiento_agua_tierra_maiz_2"
                                             :otro-rercuso="true"
                                             :consume2=" requerimiento_semilla_maiz_tierra_maiz + requerimiento_semilla_maiz_tierra_maiz_2"
                                             :src-consume2="'assets/semilla_maiz.png'"></ObtencionRecursoComponent>
                </div>
                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="traslate('granjaGallinas')"
                                             :titulo-consumo="traslate('consumo')"
                                             :titulo-produccion="traslate('produccion')"
                                             :src-produccion="'assets/huevo.png'" :src-consume="'assets/agua.png'"
                                             :produccion=" produccion_huevo"
                                             :consume="requerimiento_agua_granja_gallina"
                                             :otro-rercuso="true"
                                             :consume2=" requerimiento_bolsa_maiz_granja_gallina"
                                             :src-consume2="'assets/bolsa_maiz.png'"></ObtencionRecursoComponent>
                </div>
                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="traslate('granjaVacas')"
                                             :titulo-consumo="traslate('consumo')"
                                             :titulo-produccion="traslate('produccion')"
                                             :src-produccion="'assets/leche.png'" :src-consume="'assets/agua.png'"
                                             :produccion=" produccion_leche"
                                             :consume="requerimiento_agua_granja_vaca"
                                             :otro-rercuso="true"
                                             :consume2=" requerimiento_bolsa_trigo_granja_vaca"
                                             :src-consume2="'assets/bolsa_trigo.png'"></ObtencionRecursoComponent>
                </div>

              </div>

              <div class="row">
                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="traslate('arbolMadera')"
                                             :titulo-consumo="traslate('consumo')"
                                             :titulo-produccion="traslate('produccion')"
                                             :src-produccion="'assets/madera.png'"
                                             :produccion=" produccion_madera + produccion_madera_2 + produccion_madera_3"
                                             :src-consume="'assets/agua.png'"
                                             :consume2="0"
                                             :consume="requerimiento_agua_arboles + requerimiento_agua_arboles_2 + requerimiento_agua_arboles_3"
                                             :otro-rercuso="false"></ObtencionRecursoComponent>
                </div>
                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="traslate('molinoArboles')"
                                             :titulo-consumo="traslate('consumo')"
                                             :titulo-produccion="traslate('produccion')"
                                             :src-produccion="'assets/carbon.png'"
                                             :produccion=" produccion_carbon"
                                             :src-consume="'assets/madera.png'"
                                             :consume="molino_cant_madera"
                                             :consume2="0"
                                             :otro-rercuso="false"></ObtencionRecursoComponent>
                </div>
                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="traslate('molinoMaiz')"
                                             :titulo-consumo="traslate('consumo')"
                                             :titulo-produccion="traslate('produccion')"
                                             :src-produccion="'assets/bolsa_maiz.png'"
                                             :produccion=" produccion_bolsa_maiz"
                                             :src-consume="'assets/maiz.png'"
                                             :consume="molino_cant_maiz"
                                             :consume2="0"
                                             :otro-rercuso="false"></ObtencionRecursoComponent>
                </div>
                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="traslate('molinoTrigo')"
                                             :titulo-consumo="traslate('consumo')"
                                             :titulo-produccion="traslate('produccion')"
                                             :src-produccion="'assets/bolsa_maiz.png'"
                                             :produccion=" produccion_bolsa_trigo"
                                             :src-consume="'assets/trigo.png'"
                                             :consume="molino_cant_trigo"
                                             :consume2="0"
                                             :otro-rercuso="false"></ObtencionRecursoComponent>
                </div>
              </div>


            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="row">
      <div class="col">
        <h2 class="text-with-shadown">{{traslate('titleDatosCalcular')}} <button class="btn btn-with-background-small" @click="alerta(traslate('calcular'),traslate('infoDatosCalcula'))">?</button></h2>

      </div>
    </div>


    <div class="row">
      <div class="col">


        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>{{traslate('pozoAgua').replace(/ /g, '&nbsp;')}}</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_pozo_agua" role="switch">
              <label class="form-check-label" for="pozo_agua"></label>
            </div>
          </div>
        </div>

        <div class="form-floating">
          <select class="form-select" id="floatingSelect" aria-label="Floating label select example"
                  v-model="nivel_pozo_agua"
                  :disabled="!checked_pozo_agua"
                  @change="onChange($event,'pozo_agua')">
            <option v-for="option in pozo_agua.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">{{traslate('level')}}</label>
        </div>

        <div class="form-floating mb-3 mt-3">
          <input type="number" class="form-control" id="floatingInput" placeholder="name@example.com"
                 :disabled="calcular_recursos== true? true: !checked_pozo_agua"
                 v-model="horas_pozo_agua">
          <label for="floatingInput">{{traslate('hour')}}</label>
        </div>
      </div>

      <div class="col">

        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>{{traslate('fabricaEnegria')}}</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_fabrica_energia" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>


        <div class="form-floating">
          <select class="form-select" v-model="nivel_fabrica_energia" :disabled="!checked_fabrica_energia"
                  @change="onChange($event,'fabrica_energia')"
                  id="floatingSelect" aria-label="Floating label select example">
            <option v-for="option in fabrica_energia.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">{{traslate('level')}}</label>
        </div>


        <div class="form-floating mb-3 mt-3">
          <input type="number" class="form-control" id="floatingInput" placeholder="name@example.com"
                 :disabled="calcular_recursos== true? true: !checked_fabrica_energia"
                 v-model="horas_fabrica_energia">
          <label for="floatingInput">{{traslate('hour')}}</label>
        </div>

      </div>
      <div class="col">

        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>{{traslate('granjaGallinas')}}</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_granja_gallinas" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>

        <div class="form-floating">
          <select class="form-select" v-model="nivel_granja_gallina" :disabled="!checked_granja_gallinas"
                  @change="onChange($event,'granja_gallinas')"
                  id="floatingSelect" aria-label="Floating label select example">
            <option v-for="option in granja_gallinas.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">{{traslate('level')}}</label>
        </div>

        <div class="form-floating mb-3 mt-3">
          <input type="number" v-model="horas_granja_gallina"
                 :disabled="calcular_recursos== true? true: !checked_granja_gallinas"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">{{traslate('hour')}}</label>
        </div>


      </div>
      <div class="col">


        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>{{traslate('granjaVacas').replace(/ /g, '&nbsp;')}}</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_granja_vacas" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>

        <div class="form-floating">
          <select class="form-select" v-model="nivel_granja_vacas" :disabled="!checked_granja_vacas"
                  @change="onChange($event,'granja_vacas')"
                  id="floatingSelect"
                  aria-label="Floating label select example">
            <option v-for="option in granja_vacas.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">{{traslate('level')}}</label>
        </div>

        <div class="form-floating mb-3 mt-3">
          <input type="number" v-model="horas_granja_vacas"
                 :disabled="calcular_recursos== true? true: !checked_granja_vacas"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">{{traslate('hour')}}</label>
        </div>


      </div>
    </div>

    <div class="row">
      <div class="col">
        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>{{ traslate('tierraTrigo') }}</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_tierra_trigo_1" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>


        <div class="form-floating">
          <select class="form-select" v-model="nivel_tierra_trigo" :disabled="!checked_tierra_trigo_1"
                  @change="onChange($event,'tierra_trigo_1')"
                  id="floatingSelect" aria-label="Floating label select example">
            <option v-for="option in tierra_trigo.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">{{traslate('level')}}</label>
        </div>


        <div class="form-floating mb-3 mt-3">
          <input type="number" v-model="horas_tierra_trigo"
                 :disabled="calcular_recursos== true? true: !checked_tierra_trigo_1"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">{{traslate('hour')}}</label>
        </div>


      </div>
      <div class="col">
        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>{{traslate('tierraTrigo')}}</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" :disabled="calcular_recursos" v-model="checked_tierra_trigo_2" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>


        <div class="form-floating">
          <select class="form-select" v-model="nivel_tierra_trigo_2" :disabled="calcular_recursos== true? true:!checked_tierra_trigo_2"
                  @change="onChange($event,'tierra_trigo_2')"
                  id="floatingSelect" aria-label="Floating label select example">
            <option v-for="option in tierra_trigo.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">{{traslate('level')}}</label>
        </div>
        <div class="form-floating mb-3  mt-3">
          <input type="number" v-model="horas_tierra_trigo_2"
                 :disabled="calcular_recursos== true? true: !checked_tierra_trigo_2"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">{{traslate('hour')}}</label>
        </div>


      </div>
      <div class="col">

        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>{{ traslate('tierraMaiz') }}</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_tierra_maiz_1" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>
        <div class="form-floating">
          <select class="form-select" v-model="nivel_tierra_maiz" :disabled="!checked_tierra_maiz_1"
                  @change="onChange($event,'tierra_maiz_1')"
                  id="floatingSelect"
                  aria-label="Floating label select example">
            <option v-for="option in tierra_maiz.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">{{traslate('level')}}</label>
        </div>
        <div class="form-floating mb-3  mt-3">
          <input type="number" v-model="horas_tierra_maiz"
                 :disabled="calcular_recursos== true? true: !checked_tierra_maiz_1"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">{{traslate('hour')}}</label>
        </div>


      </div>
      <div class="col">
        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>{{ traslate('tierraMaiz') }}</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" :disabled="calcular_recursos" v-model="checked_tierra_maiz_2" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>
        <div class="form-floating">
          <select class="form-select" v-model="nivel_tierra_maiz_2" :disabled="calcular_recursos== true? true: !checked_tierra_maiz_2"
                  @change="onChange($event,'tierra_maiz_2')"
                  id="floatingSelect" aria-label="Floating label select example">
            <option v-for="option in tierra_maiz.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">{{traslate('level')}}</label>
        </div>
        <div class="form-floating mb-3  mt-3">
          <input type="number" v-model="horas_tierra_maiz_2"
                 :disabled="calcular_recursos== true? true: !checked_tierra_maiz_2"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">{{traslate('hour')}}</label>
        </div>
      </div>
    </div>

    <div class="row">
      <div class="col">

        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>{{traslate('arbolMadera')}}</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_arboles_1" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>

        <div class="form-floating">
          <select class="form-select" v-model="nivel_arboles" :disabled="!checked_arboles_1"
                  @change="onChange($event,'arboles_1')"
                  id="floatingSelect"
                  aria-label="Floating label select example">
            <option v-for="option in arboles.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">{{traslate('level')}}</label>
        </div>
        <div class="form-floating mb-3 mt-3">
          <input type="number" v-model="horas_arboles"
                 :disabled="calcular_recursos== true? true: !checked_arboles_1"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">{{traslate('hour')}}</label>
        </div>

      </div>

      <div class="col">

        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>{{traslate('arbolMadera')}}</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" :disabled="calcular_recursos" v-model="checked_arboles_2" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>

        <div class="form-floating">
          <select class="form-select" v-model="nivel_arboles_2" :disabled="calcular_recursos== true? true: !checked_arboles_2"
                  @change="onChange($event,'arboles_2')"
                  id="floatingSelect"
                  aria-label="Floating label select example">
            <option v-for="option in arboles.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">{{traslate('level')}}</label>
        </div>
        <div class="form-floating mb-3 mt-3">
          <input type="number" v-model="horas_arboles_2"
                 :disabled="calcular_recursos== true? true: !checked_arboles_2"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">{{traslate('hour')}}</label>
        </div>
      </div>

      <div class="col">
        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>{{traslate('arbolMadera')}}</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" :disabled="calcular_recursos" v-model="checked_arboles_3" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>

        <div class="form-floating">
          <select class="form-select" v-model="nivel_arboles_3" :disabled="calcular_recursos== true? true:  !checked_arboles_3"
                  @change="onChange($event,'arboles_3')"
                  id="floatingSelect"
                  aria-label="Floating label select example">
            <option v-for="option in arboles.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">{{traslate('level')}}</label>
        </div>

        <div class="form-floating mb-3 mt-3">
          <input type="number" v-model="horas_arboles_3"
                 :disabled="calcular_recursos== true? true: !checked_arboles_3"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">{{traslate('hour')}}</label>
        </div>

      </div>
    </div>

    <div class="row text-center">
      <h2 class="text-with-shadown">{{traslate('molino')}}</h2>
      <div class="col">


        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>{{traslate('madera')}}</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_molino_madera" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>

        <label class="text-with-shadown">{{ molino.madera.tiempo }} {{traslate('hour')}}</label>
        <div class="form-floating mb-3">
          <input type="number" v-model="molino_cant_madera"
                 :disabled="calcular_recursos== true? true: !checked_molino_madera"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">{{traslate('cantidad')}}</label>
        </div>
      </div>
      <div class="col">


        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>{{traslate('maiz')}}</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_molino_maiz" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>
        <label class="text-with-shadown">{{ molino.maiz.tiempo }} {{traslate('hour')}}</label>
        <div class="form-floating mb-3">
          <input type="number" v-model="molino_cant_maiz"
                 :disabled="calcular_recursos== true? true: !checked_molino_maiz"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">{{traslate('cantidad')}}</label>
        </div>
      </div>

      <div class="col">
        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>{{traslate('trigo')}}</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_molino_trigo" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>

        <label class="text-with-shadown">{{ molino.trigo.tiempo }} {{traslate('hour')}}</label>
        <div class="form-floating mb-3">
          <input type="number" v-model="molino_cant_trigo"
                 :disabled="calcular_recursos== true? true: !checked_molino_trigo"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">{{traslate('cantidad')}}</label>
        </div>
      </div>

      <div class="col">

        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>{{traslate('leche')}}</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_molino_leche" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>
        <label class="text-with-shadown">{{ molino.leche.tiempo }} {{traslate('hour')}}</label>
        <div class="form-floating mb-3">
          <input type="number" v-model="molino_cant_leche"
                 :disabled="calcular_recursos== true? true: !checked_molino_leche"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">{{traslate('cantidad')}}</label>
        </div>
      </div>
      <div class="col">

        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>{{traslate('huevo')}}</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_molino_huevo" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>
        <label class="text-with-shadown">{{ molino.huevo.tiempo }} {{traslate('hour')}}</label>
        <div class="form-floating mb-3">
          <input type="number" v-model="molino_cant_huevo"
                 :disabled="calcular_recursos== true? true: !checked_molino_huevo"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">{{traslate('cantidad')}}</label>
        </div>
      </div>
    </div>

  </div>

</template>


<script setup>
import {ref, computed, onMounted, onBeforeUpdate} from 'vue'
import RecursoComponent from "../components/RecursoComponent.vue";
import ObtencionRecursoComponent from "../components/ObtencionRecursoComponent.vue";
import en from "./en"
import es from "./es"

const pozo_agua = {
  nivel: {
    1: {
      nivel: 1,
      produccion: 1,
      tiempo: 4,
      requerimiento: {
        energia: 1,
      },
      almacenamiento: 8
    },
    2: {
      nivel: 2,
      produccion: 1,
      tiempo: 3,
      requerimiento: {
        energia: 1,
      },
      almacenamiento: 8
    },
    3: {
      nivel: 3,
      produccion: 1,
      tiempo: 1.11,
      requerimiento: {
        energia: 1,
      },
      almacenamiento: 8
    },
    4: {
      nivel: 4,
      produccion: 1,
      tiempo: 0.51,
      requerimiento: {
        energia: 1,
      },
      almacenamiento: 8
    }
  }
};

const fabrica_energia = {
  nivel: {
    1: {
      nivel: 1,
      produccion: 1,
      tiempo: 4,
      requerimiento: {
        carbon: 2,
      },
      almacenamiento: 8
    },
    2: {
      nivel: 2,
      produccion: 1,
      tiempo: 3,
      requerimiento: {
        carbon: 2,
      },
      almacenamiento: 8
    },
    3: {
      nivel: 3,
      produccion: 1,
      tiempo: 1.11,
      requerimiento: {
        carbon: 2,
      },
      almacenamiento: 8
    },
    4: {
      nivel: 4,
      produccion: 1,
      tiempo: 0.51,
      requerimiento: {
        carbon: 2,
      },
      almacenamiento: 8
    }
  }
};

const granja_gallinas = {
  nivel: {
    1: {
      nivel: 1,
      produccion: 2,
      tiempo: 12,
      requerimiento: {
        bolsa_maiz: 1,
        agua: 2,
      }
    },
    2: {
      nivel: 2,
      produccion: 4,
      tiempo: 12,
      requerimiento: {
        bolsa_maiz: 2,
        agua: 4,
      }
    },
    3: {
      nivel: 3,
      produccion: 6,
      tiempo: 12,
      requerimiento: {
        bolsa_maiz: 3,
        agua: 6,
      }
    },
    4: {
      nivel: 4,
      produccion: 8,
      tiempo: 12,
      requerimiento: {
        bolsa_maiz: 4,
        agua: 8,
      }
    }
  }
};

const granja_vacas = {
  nivel: {
    1: {
      nivel: 1,
      produccion: 2,
      tiempo: 24,
      requerimiento: {
        bolsa_trigo: 2,
        agua: 3,
      }
    },
    2: {
      nivel: 2,
      produccion: 4,
      tiempo: 24,
      requerimiento: {
        bolsa_trigo: 4,
        agua: 6,
      }
    },
    3: {
      nivel: 3,
      produccion: 6,
      tiempo: 24,
      requerimiento: {
        bolsa_trigo: 6,
        agua: 9,
      }
    },
    4: {
      nivel: 4,
      produccion: 8,
      tiempo: 24,
      requerimiento: {
        bolsa_trigo: 12,
        agua: 8,
      }
    }
  }
};

const tierra_maiz = {
  nivel: {
    1: {
      nivel: 1,
      produccion: 5,
      tiempo: 48,
      requerimiento: {
        semilla_maiz: 1,
        agua: 4,

      },
    },
    2: {
      nivel: 2,
      produccion: 10,
      tiempo: 48,
      requerimiento: {
        semilla_maiz: 2,
        agua: 8,
      },
    },
    3: {
      nivel: 3,
      produccion: 15,
      tiempo: 48,
      requerimiento: {
        semilla_maiz: 3,
        agua: 12,
      },
    },
    4: {
      nivel: 4,
      produccion: 20,
      tiempo: 48,
      requerimiento: {
        semilla_maiz: 4,
        agua: 16,
      },
    }
  }
};

const tierra_trigo = {
  nivel: {
    1: {
      nivel: 1,
      produccion: 2,
      tiempo: 24,
      requerimiento: {
        semilla_trigo: 1,
        agua: 1,

      },
    },
    2: {
      nivel: 2,
      produccion: 4,
      tiempo: 24,
      requerimiento: {
        semilla_trigo: 2,
        agua: 2,
      },
    },
    3: {
      nivel: 3,
      produccion: 6,
      tiempo: 24,
      requerimiento: {
        semilla_trigo: 3,
        agua: 3,
      },
    },
    4: {
      nivel: 4,
      produccion: 20,
      tiempo: 24,
      requerimiento: {
        semilla_trigo: 4,
        agua: 4,
      },
    }
  }
};

const arboles = {
  nivel: {
    1: {
      nivel: 1,
      produccion: 5,
      tiempo: 72,
      requerimiento: {
        agua: 10,
      },
    },
    2: {
      nivel: 2,
      produccion: 10,
      tiempo: 72,
      requerimiento: {
        agua: 20,
      }
    },
    3: {
      nivel: 3,
      produccion: 15,
      tiempo: 72,
      requerimiento: {
        agua: 30,
      }
    },
    4: {
      nivel: 4,
      produccion: 20,
      tiempo: 72,
      requerimiento: {
        agua: 40,
      }
    }

  }
};

const molino = {
  madera: {
    min: 2,
    max: 20,
    tiempo: 24,
    ratio: 8,
    fee: 1,
  },
  maiz: {
    min: 2,
    max: 20,
    tiempo: 72,
    ratio: 0.5,
    fee: 1,
  },
  trigo: {
    min: 1,
    max: 20,
    tiempo: 48,
    ratio: 1,
    fee: 1,
  },
  leche: {
    min: 4,
    max: 40,
    tiempo: 72,
    ratio: 2.5,
    fee: 1,
  },
  huevo: {
    min: 4,
    max: 40,
    tiempo: 72,
    ratio: 125,
    fee: 1,
  },
}

const idioma_escoje={
  ES:es.data().es,
  EN:en.data().en
}
let idioma=ref('EN');

onMounted(()=>{
  document.documentElement.lang=idioma.value.toLowerCase();
})

onBeforeUpdate(()=>{
  document.documentElement.lang=idioma.value.toLowerCase();
})

let nivel_pozo_agua = ref(1);
let horas_pozo_agua = ref(4);
let produccion_agua = ref(0);
let requerimiento_energia_pozo = ref(0);

let nivel_fabrica_energia = ref(1);
let horas_fabrica_energia = ref(4);
let produccion_energia = ref(0);
let requerimiento_carbon_fabrica = ref(0);

let nivel_tierra_maiz = ref(1);
let horas_tierra_maiz = ref(48);
let produccion_maiz = ref(0);
let requerimiento_semilla_maiz_tierra_maiz = ref(0);
let requerimiento_agua_tierra_maiz = ref(0);

let nivel_tierra_maiz_2 = ref(1);
let horas_tierra_maiz_2 = ref(48);
let produccion_maiz_2 = ref(0);
let requerimiento_semilla_maiz_tierra_maiz_2 = ref(0);
let requerimiento_agua_tierra_maiz_2 = ref(0);

let nivel_tierra_trigo = ref(1);
let horas_tierra_trigo = ref(24);
let produccion_trigo = ref(0);
let requerimiento_semilla_trigo_tierra_trigo = ref(0);
let requerimiento_agua_tierra_trigo = ref(0);

let nivel_tierra_trigo_2 = ref(1);
let horas_tierra_trigo_2 = ref(24);
let produccion_trigo_2 = ref(0);
let requerimiento_semilla_trigo_tierra_trigo_2 = ref(0);
let requerimiento_agua_tierra_trigo_2 = ref(0);

let nivel_granja_gallina = ref(1);
let horas_granja_gallina = ref(12);
let produccion_huevo = ref(0);
let requerimiento_bolsa_maiz_granja_gallina = ref(0);
let requerimiento_agua_granja_gallina = ref(0);

let nivel_granja_vacas = ref(1);
let horas_granja_vacas = ref(24);
let produccion_leche = ref(0);
let requerimiento_bolsa_trigo_granja_vaca = ref(0);
let requerimiento_agua_granja_vaca = ref(0);

let nivel_arboles = ref(1);
let horas_arboles = ref(72);
let produccion_madera = ref(0);
let requerimiento_agua_arboles = ref(0);

let nivel_arboles_2 = ref(1);
let horas_arboles_2 = ref(72);
let produccion_madera_2 = ref(0);
let requerimiento_agua_arboles_2 = ref(0);

let nivel_arboles_3 = ref(1);
let horas_arboles_3 = ref(72);
let produccion_madera_3 = ref(0);
let requerimiento_agua_arboles_3 = ref(0);

let molino_cant_madera = ref(0);
let produccion_carbon = ref(0)

let molino_cant_maiz = ref(0);
let produccion_bolsa_maiz = ref(0)

let molino_cant_trigo = ref(0);
let produccion_bolsa_trigo = ref(0)

let molino_cant_leche = ref(0);
let produccion_kod = ref(0)

let molino_cant_huevo = ref(0);
let produccion_hueso = ref(0)

let total_energia = ref(0)
let total_agua = ref(0)
let total_maiz = ref(0)
let total_trigo = ref(0)
let total_leche = ref(0)
let total_bolsa_maiz = ref(0)
let total_bolsa_trigo = ref(0)
let total_huevo = ref(0)
let total_madera = ref(0)
let total_carbon = ref(0)
let total_kod = ref(0)
let total_hueso = ref(0)

let inicial_energia = ref(0)
let inicial_agua = ref(0)
let inicial_semilla_maiz = ref(0)
let inicial_semilla_trigo = ref(0)
let inicial_maiz = ref(0)
let inicial_trigo = ref(0)
let inicial_bolsa_maiz = ref(0)
let inicial_bolsa_trigo = ref(0)
let inicial_leche = ref(0)
let inicial_huevo = ref(0)
let inicial_madera = ref(0)
let inicial_carbon = ref(0)

let consumo_energia = ref(0)
let consumo_agua = ref(0)
let consumo_semilla_maiz = ref(0)
let consumo_semilla_trigo = ref(0)
let consumo_maiz = ref(0)
let consumo_trigo = ref(0)
let consumo_bolsa_maiz = ref(0)
let consumo_bolsa_trigo = ref(0)
let consumo_leche = ref(0)
let consumo_huevo = ref(0)
let consumo_madera = ref(0)
let consumo_carbon = ref(0)

let checked_pozo_agua = ref(false);
let checked_fabrica_energia = ref(false);
let checked_tierra_trigo_1 = ref(false);
let checked_tierra_trigo_2 = ref(false);
let checked_tierra_maiz_1 = ref(false);
let checked_tierra_maiz_2 = ref(false);
let checked_granja_gallinas = ref(false);
let checked_granja_vacas = ref(false);
let checked_arboles_1 = ref(false);
let checked_arboles_2 = ref(false);
let checked_arboles_3 = ref(false);
let checked_molino_madera = ref(false);
let checked_molino_maiz = ref(false);
let checked_molino_trigo = ref(false);
let checked_molino_leche = ref(false);
let checked_molino_huevo = ref(false);

let calcular_recursos = ref(false);

function calcular() {

  let recursos_inicial_agua=inicial_agua.value;

  let agua = pozo_agua.nivel[nivel_pozo_agua.value];
  if(calcular_recursos.value && checked_pozo_agua.value){
    requerimiento_energia_pozo.value=inicial_energia.value;
    produccion_agua.value=inicial_energia.value/agua.requerimiento.energia;
    horas_pozo_agua.value=agua.tiempo*(inicial_energia.value/agua.requerimiento.energia);
  }else{
    produccion_agua.value = (horas_pozo_agua.value <= 0 || !checked_pozo_agua.value) ? 0 : parseFloat(horas_pozo_agua.value) / (agua.tiempo * agua.produccion)
    requerimiento_energia_pozo.value = (horas_pozo_agua.value <= 0 || !checked_pozo_agua.value) ? 0 : parseFloat(horas_pozo_agua.value) / (agua.tiempo * agua.requerimiento.energia)
  }

  let energia = fabrica_energia.nivel[nivel_fabrica_energia.value];
  if(calcular_recursos.value && checked_fabrica_energia.value){
    requerimiento_carbon_fabrica.value=inicial_carbon.value;
    produccion_energia.value=inicial_carbon.value/energia.requerimiento.carbon;
    horas_fabrica_energia.value=energia.tiempo*(inicial_carbon.value/energia.requerimiento.carbon);
  }else{
    produccion_energia.value = (horas_fabrica_energia.value <= 0 || !checked_fabrica_energia.value) ? 0 : parseFloat(horas_fabrica_energia.value) / (energia.tiempo / energia.produccion)
    requerimiento_carbon_fabrica.value = (horas_fabrica_energia.value <= 0 || !checked_fabrica_energia.value) ? 0 : parseFloat(horas_fabrica_energia.value) / (energia.tiempo / energia.requerimiento.carbon)
  }

  let maiz = tierra_maiz.nivel[nivel_tierra_maiz.value];
  if(calcular_recursos.value && checked_tierra_maiz_1.value){
    let ciclos_completos_agua=0;
    let ciclos_completos_semilla=0;
    ciclos_completos_agua=(recursos_inicial_agua/maiz.requerimiento.agua);
    ciclos_completos_semilla=(inicial_semilla_maiz.value/maiz.requerimiento.semilla_maiz);

    requerimiento_semilla_maiz_tierra_maiz.value= Math.min(ciclos_completos_semilla, ciclos_completos_agua) * maiz.requerimiento.semilla_maiz;
    requerimiento_agua_tierra_maiz.value= Math.min(ciclos_completos_semilla, ciclos_completos_agua) * maiz.requerimiento.agua;


    recursos_inicial_agua-= (Math.min(ciclos_completos_semilla, ciclos_completos_agua)*maiz.requerimiento.agua);

    produccion_maiz.value=maiz.produccion * (Math.min(ciclos_completos_semilla, ciclos_completos_agua));
    horas_tierra_maiz.value=maiz.tiempo*Math.min(ciclos_completos_semilla, ciclos_completos_agua);
  }else {
    produccion_maiz.value = (horas_tierra_maiz.value <= 0 || !checked_tierra_maiz_1.value) ? 0 : parseFloat(horas_tierra_maiz.value) / (maiz.tiempo / maiz.produccion)
    requerimiento_semilla_maiz_tierra_maiz.value = (horas_tierra_maiz.value <= 0 || !checked_tierra_maiz_1.value) ? 0 : parseFloat(horas_tierra_maiz.value) / (maiz.tiempo / maiz.requerimiento.semilla_maiz)
    requerimiento_agua_tierra_maiz.value = (horas_tierra_maiz.value <= 0 || !checked_tierra_maiz_1.value) ? 0 : parseFloat(horas_tierra_maiz.value) / (maiz.tiempo / maiz.requerimiento.agua)
  }

  let maiz_2 = tierra_maiz.nivel[nivel_tierra_maiz_2.value];
  produccion_maiz_2.value = (horas_tierra_maiz_2.value <= 0 || !checked_tierra_maiz_2.value) ? 0 : parseFloat(horas_tierra_maiz_2.value) / (maiz_2.tiempo / maiz_2.produccion)
  requerimiento_semilla_maiz_tierra_maiz_2.value = (horas_tierra_maiz_2.value <= 0 || !checked_tierra_maiz_2.value) ? 0 : parseFloat(horas_tierra_maiz_2.value) / (maiz_2.tiempo / maiz_2.requerimiento.semilla_maiz)
  requerimiento_agua_tierra_maiz_2.value = (horas_tierra_maiz_2.value <= 0 || !checked_tierra_maiz_2.value) ? 0 : parseFloat(horas_tierra_maiz_2.value) / (maiz_2.tiempo / maiz_2.requerimiento.agua)

  let trigo = tierra_trigo.nivel[nivel_tierra_trigo.value];
  if(calcular_recursos.value && checked_tierra_trigo_1.value){


    let ciclos_completos_agua=0;
    let ciclos_completos_semilla=0;
    ciclos_completos_agua=(recursos_inicial_agua/trigo.requerimiento.agua);
    ciclos_completos_semilla=(inicial_semilla_trigo.value/trigo.requerimiento.semilla_trigo);

    requerimiento_semilla_trigo_tierra_trigo.value= (Math.min(ciclos_completos_semilla, ciclos_completos_agua)) * trigo.requerimiento.semilla_trigo;
    requerimiento_agua_tierra_trigo.value= (Math.min(ciclos_completos_semilla, ciclos_completos_agua)) * trigo.requerimiento.agua;

    recursos_inicial_agua-= (Math.min(ciclos_completos_semilla, ciclos_completos_agua)*maiz.requerimiento.agua);

    produccion_trigo.value=trigo.produccion *(Math.min(ciclos_completos_semilla, ciclos_completos_agua));
    horas_tierra_trigo.value=trigo.tiempo*(Math.min(ciclos_completos_semilla, ciclos_completos_agua));
  }else {
    produccion_trigo.value = (horas_tierra_trigo.value <= 0 || !checked_tierra_trigo_1.value) ? 0 : parseFloat(horas_tierra_trigo.value) / (trigo.tiempo / trigo.produccion)
    requerimiento_semilla_trigo_tierra_trigo.value = (horas_tierra_trigo.value <= 0 || !checked_tierra_trigo_1.value) ? 0 : parseFloat(horas_tierra_trigo.value) / (trigo.tiempo / trigo.requerimiento.semilla_trigo)
    requerimiento_agua_tierra_trigo.value = (horas_tierra_trigo.value <= 0 || !checked_tierra_trigo_1.value) ? 0 : parseFloat(horas_tierra_trigo.value) / (trigo.tiempo / trigo.requerimiento.agua)
  }

  let trigo_2 = tierra_trigo.nivel[nivel_tierra_trigo_2.value];
  produccion_trigo_2.value = (horas_tierra_trigo_2.value <= 0 || !checked_tierra_trigo_2.value) ? 0 : parseFloat(horas_tierra_trigo_2.value) / (trigo_2.tiempo / trigo_2.produccion)
  requerimiento_semilla_trigo_tierra_trigo_2.value = (horas_tierra_trigo_2.value <= 0 || !checked_tierra_trigo_2.value) ? 0 : parseFloat(horas_tierra_trigo_2.value) / (trigo_2.tiempo / trigo_2.requerimiento.semilla_trigo)
  requerimiento_agua_tierra_trigo_2.value = (horas_tierra_trigo_2.value <= 0 || !checked_tierra_trigo_2.value) ? 0 : parseFloat(horas_tierra_trigo_2.value) / (trigo_2.tiempo / trigo_2.requerimiento.agua)


  let huevo = granja_gallinas.nivel[nivel_granja_gallina.value];
  if(calcular_recursos.value && checked_granja_gallinas.value){

    let ciclos_completos_agua=0;
    let ciclos_completos_semilla=0;
    ciclos_completos_agua=(inicial_agua.value/huevo.requerimiento.agua);
    ciclos_completos_semilla=(inicial_bolsa_maiz.value/huevo.requerimiento.bolsa_maiz);

    requerimiento_bolsa_maiz_granja_gallina.value=(Math.min(ciclos_completos_semilla, ciclos_completos_agua))* huevo.requerimiento.bolsa_maiz;
    requerimiento_agua_granja_gallina.value=(Math.min(ciclos_completos_semilla, ciclos_completos_agua))* huevo.requerimiento.agua;

    recursos_inicial_agua-= (Math.min(ciclos_completos_semilla, ciclos_completos_agua)*huevo.requerimiento.agua);

    produccion_huevo.value=huevo.produccion *(Math.min(ciclos_completos_semilla, ciclos_completos_agua));
    horas_granja_gallina.value=huevo.tiempo*(Math.min(ciclos_completos_semilla, ciclos_completos_agua));
  }else {
    produccion_huevo.value = (horas_granja_gallina.value <= 0 || !checked_granja_gallinas.value) ? 0 : parseFloat(horas_granja_gallina.value) / (huevo.tiempo / huevo.produccion)
    requerimiento_bolsa_maiz_granja_gallina.value = (horas_granja_gallina.value <= 0 || !checked_granja_gallinas.value) ? 0 : parseFloat(horas_granja_gallina.value) / (huevo.tiempo / huevo.requerimiento.bolsa_maiz)
    requerimiento_agua_granja_gallina.value = (horas_granja_gallina.value <= 0 || !checked_granja_gallinas.value) ? 0 : parseFloat(horas_granja_gallina.value) / (huevo.tiempo / huevo.requerimiento.agua)
  }

  let leche = granja_vacas.nivel[nivel_granja_vacas.value];
  if(calcular_recursos.value && checked_granja_vacas.value){

    let ciclos_completos_agua=0;
    let ciclos_completos_semilla=0;
    ciclos_completos_agua=(inicial_agua.value/leche.requerimiento.agua);
    ciclos_completos_semilla=(inicial_bolsa_trigo.value/leche.requerimiento.bolsa_trigo);

    requerimiento_bolsa_trigo_granja_vaca.value=(Math.min(ciclos_completos_semilla, ciclos_completos_agua))*leche.requerimiento.bolsa_trigo;
    requerimiento_agua_granja_vaca.value=(Math.min(ciclos_completos_semilla, ciclos_completos_agua))*leche.requerimiento.agua;

    recursos_inicial_agua-= (Math.min(ciclos_completos_semilla, ciclos_completos_agua)*leche.requerimiento.agua);

    produccion_leche.value=leche.produccion *(Math.min(ciclos_completos_semilla, ciclos_completos_agua));
    horas_granja_vacas.value=leche.tiempo*(Math.min(ciclos_completos_semilla, ciclos_completos_agua));
  }else {
    produccion_leche.value = (horas_granja_vacas.value <= 0 || !checked_granja_vacas.value) ? 0 : parseFloat(horas_granja_vacas.value) / (leche.tiempo / leche.produccion)
    requerimiento_bolsa_trigo_granja_vaca.value = (horas_granja_vacas.value <= 0 || !checked_granja_vacas.value) ? 0 : parseFloat(horas_granja_vacas.value) / (leche.tiempo / leche.requerimiento.bolsa_trigo)
    requerimiento_agua_granja_vaca.value = (horas_granja_vacas.value <= 0 || !checked_granja_vacas.value) ? 0 : parseFloat(horas_granja_vacas.value) / (leche.tiempo / leche.requerimiento.agua)
  }

  let madera = arboles.nivel[nivel_arboles.value];
  if(calcular_recursos.value && checked_arboles_1.value){
    requerimiento_agua_arboles.value= (inicial_agua.value/madera.requerimiento.agua) * madera.requerimiento.agua;

    recursos_inicial_agua-= (inicial_agua.value/madera.requerimiento.agua) * madera.requerimiento.agua;

    produccion_madera.value=madera.produccion *(inicial_agua.value/madera.requerimiento.agua);
    horas_arboles.value=madera.tiempo*(inicial_agua.value/madera.requerimiento.agua);
  }else {
    produccion_madera.value = (horas_arboles.value <= 0 || !checked_arboles_1.value) ? 0 : parseFloat(horas_arboles.value) / (madera.tiempo / madera.produccion)
    requerimiento_agua_arboles.value = (horas_arboles.value <= 0 || !checked_arboles_1.value) ? 0 : parseFloat(horas_arboles.value) / (madera.tiempo / madera.requerimiento.agua)
  }

  let madera_2 = arboles.nivel[nivel_arboles_2.value];
  produccion_madera_2.value = (horas_arboles_2.value <= 0 || !checked_arboles_2.value) ? 0 : parseFloat(horas_arboles_2.value) / (madera_2.tiempo / madera_2.produccion)
  requerimiento_agua_arboles_2.value = (horas_arboles_2.value <= 0 || !checked_arboles_2.value) ? 0 : parseFloat(horas_arboles_2.value) / (madera_2.tiempo / madera_2.requerimiento.agua)

  let madera_3 = arboles.nivel[nivel_arboles_3.value];
  produccion_madera_3.value = (horas_arboles_3.value <= 0 || !checked_arboles_3.value) ? 0 : parseFloat(horas_arboles_3.value) / (madera_3.tiempo / madera_3.produccion)
  requerimiento_agua_arboles_3.value = (horas_arboles_3.value <= 0 || !checked_arboles_3.value) ? 0 : parseFloat(horas_arboles_3.value) / (madera_3.tiempo / madera_3.requerimiento.agua)

  let carbon = molino.madera;
  if(calcular_recursos.value && checked_molino_madera.value){
    produccion_carbon.value = (!checked_molino_madera.value) ? 0 : carbon.ratio * inicial_madera.value;
    molino_cant_madera.value = (!checked_molino_madera.value) ? 0 : inicial_madera.value;
  }else {
    produccion_carbon.value = (!checked_molino_madera.value) ? 0 : carbon.ratio * molino_cant_madera.value;
    molino_cant_madera.value = (!checked_molino_madera.value) ? 0 : molino_cant_madera.value;
  }

  let bolsa_maiz = molino.maiz;
  if(calcular_recursos.value && checked_molino_maiz.value){
    produccion_bolsa_maiz.value = (!checked_molino_maiz.value) ? 0 : bolsa_maiz.ratio * inicial_maiz.value;
    molino_cant_maiz.value = (!checked_molino_maiz.value) ? 0 : inicial_maiz.value;
  }else {
    produccion_bolsa_maiz.value = (!checked_molino_maiz.value) ? 0 : bolsa_maiz.ratio * molino_cant_maiz.value;
    molino_cant_maiz.value = (!checked_molino_maiz.value) ? 0 : molino_cant_maiz.value;
  }

  let bolsa_trigo = molino.trigo;
  if(calcular_recursos.value && checked_molino_trigo.value){
    produccion_bolsa_trigo.value = (!checked_molino_trigo.value) ? 0 : bolsa_trigo.ratio * inicial_trigo.value;
    molino_cant_trigo.value = (!checked_molino_trigo.value) ? 0 : inicial_trigo.value;
  }else {
    produccion_bolsa_trigo.value = (!checked_molino_trigo.value) ? 0 : bolsa_trigo.ratio * molino_cant_trigo.value;
    molino_cant_trigo.value = (!checked_molino_trigo.value) ? 0 : molino_cant_trigo.value;
  }

  let kod = molino.leche;
  if(calcular_recursos.value && checked_molino_leche.value){
    produccion_kod.value = (!checked_molino_leche.value) ? 0 : kod.ratio * inicial_leche.value;
    molino_cant_leche.value = (!checked_molino_leche.value) ? 0 : inicial_leche.value;
  }else {
    produccion_kod.value = (!checked_molino_leche.value) ? 0 : kod.ratio * molino_cant_leche.value;
    molino_cant_leche.value = (!checked_molino_leche.value) ? 0 : molino_cant_leche.value;
  }

  let hueso = molino.huevo;
  if(calcular_recursos.value && checked_molino_huevo.value){
    produccion_hueso.value = (!checked_molino_huevo.value) ? 0 : hueso.ratio * inicial_huevo.value;
    molino_cant_huevo.value = (!checked_molino_huevo.value) ? 0 : inicial_huevo.value;
  }else {
    produccion_hueso.value = (!checked_molino_huevo.value) ? 0 : hueso.ratio * molino_cant_huevo.value;
    molino_cant_huevo.value = (!checked_molino_huevo.value) ? 0 : molino_cant_huevo.value;
  }

  total_energia.value = produccion_energia.value;
  total_agua.value = produccion_agua.value;
  total_maiz.value = produccion_maiz.value + produccion_maiz_2.value;
  total_trigo.value = produccion_trigo.value + produccion_trigo_2.value;
  total_bolsa_maiz.value = produccion_bolsa_maiz.value;
  total_bolsa_trigo.value = produccion_bolsa_trigo.value;
  total_huevo.value = produccion_huevo.value;
  total_leche.value = produccion_leche.value;
  total_madera.value = produccion_madera.value + produccion_madera_2.value + produccion_madera_3.value;
  total_carbon.value = produccion_carbon.value;
  total_kod.value = produccion_kod.value;
  total_hueso.value = produccion_hueso.value

  consumo_energia.value = requerimiento_energia_pozo.value;
  consumo_agua.value = requerimiento_agua_tierra_maiz.value + requerimiento_agua_tierra_maiz_2.value
      + requerimiento_agua_tierra_trigo.value + requerimiento_agua_tierra_trigo_2.value
      + requerimiento_agua_granja_gallina.value + requerimiento_agua_granja_vaca.value
      + requerimiento_agua_arboles.value + requerimiento_agua_arboles_2.value + requerimiento_agua_arboles_3.value;
  consumo_semilla_maiz.value = requerimiento_semilla_maiz_tierra_maiz.value + requerimiento_semilla_maiz_tierra_maiz_2.value;
  consumo_semilla_trigo.value = requerimiento_semilla_trigo_tierra_trigo.value + requerimiento_semilla_trigo_tierra_trigo_2.value;
  consumo_maiz.value = molino_cant_maiz.value;
  consumo_trigo.value = molino_cant_trigo.value;
  consumo_bolsa_trigo.value = requerimiento_bolsa_trigo_granja_vaca.value;
  consumo_bolsa_maiz.value = requerimiento_bolsa_maiz_granja_gallina.value;
  consumo_madera.value = molino_cant_madera.value;
  consumo_carbon.value = requerimiento_carbon_fabrica.value;
  consumo_leche.value = molino_cant_leche.value;
  consumo_huevo.value = molino_cant_huevo.value;

}

function onChangeRecursos(event) {
  checked_arboles_2.value=checked_arboles_3.value=checked_tierra_trigo_2.value=checked_tierra_maiz_2.value=!event.target.value;
}


function onChange(event, tipo) {

  switch (tipo) {
    case 'pozo_agua':
      horas_pozo_agua.value = pozo_agua.nivel[event.target.value].tiempo;
      break;
    case 'fabrica_energia':
      horas_fabrica_energia.value = fabrica_energia.nivel[event.target.value].tiempo;
      break;
    case 'granja_gallinas':
      horas_granja_gallina.value = granja_gallinas.nivel[event.target.value].tiempo;
      break;
    case 'granja_vacas':
      horas_granja_vacas.value = granja_vacas.nivel[event.target.value].tiempo;
      break;
    case 'tierra_trigo_1':
      horas_tierra_trigo.value = tierra_trigo.nivel[event.target.value].tiempo;
      break;
    case 'tierra_trigo_2':
      horas_tierra_trigo_2.value = tierra_trigo.nivel[event.target.value].tiempo;
      break;
    case 'tierra_maiz_1':
      horas_tierra_maiz.value = tierra_maiz.nivel[event.target.value].tiempo;
      break;
    case 'tierra_maiz_2':
      horas_tierra_maiz_2.value = tierra_maiz.nivel[event.target.value].tiempo;
      break;
    case 'arboles_1':
      horas_arboles.value = arboles.nivel[event.target.value].tiempo;
      break;
    case 'arboles_2':
      horas_arboles_2.value = arboles.nivel[event.target.value].tiempo;
      break;
    case 'arboles_3':
      horas_arboles_3.value = arboles.nivel[event.target.value].tiempo;
      break;
    default:

  }

}

function restar(a, b) {
  return a - b
}

function alerta(title,msg){
  Swal.fire(
      title,
      msg,
      'question'
  )
}

function traslate(msg){
  return idioma_escoje[idioma.value][msg];
}



</script>

<style>

body {
  /*background: #a18262 !important;*/
  background: url('../assets/liso.png') repeat;
  background-clip: padding-box;
  background-origin: initial;
  background-position: 50%;
  border-image-repeat: repeat;
  border-image-slice: 8 8 8 8;
  border-image-source: url('../assets/detalle.png');
  border-image-width: 18px;
  border-style: solid;
  border-width: 15px;
  padding: 12px;
}

.text-with-shadown {
  color: white !important;
  text-shadow: 0px 0px 5px black;
}

.caja-cafe {
  background: #854C30;
  background-clip: padding-box;
  background-origin: initial;
  background-position: 50%;
  border-image-repeat: repeat;
  border-image-slice: 4 4 4 4;
  border-image-source: url('../assets/cafeBorde.png');
  border-image-width: 18px;
  border-style: solid;
  border-width: 15px;
  padding: 12px;
}

.relleno-cafe {
  background: #D27D2C !important;
}

.btn-with-background {
  background-image: url('../assets/button.png');
  background-size: 100% 100%;
  background-position: center center;
  text-align: center !important;
  color: white !important;
  font-weight: bold !important;
  padding: 1% 3% !important;
}

.btn-with-background-small {
  background-image: url('../assets/button.png');
  background-size: 100% 100%;
  background-position: center center;
  text-align: center !important;
  color: white !important;
  font-weight: bold !important;
  padding: 0.5% 1% !important;
}

.boton-imagen {
  display: inline-block;
  position: relative;
}

.boton-imagen img {
  display: block;
  max-width: 100%;
}

.texto-boton {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 14px;
  color: white;
}

.form-floating label {
  background-color: transparent !important;
  color: white;
  font-weight: bold;
}


.form-floating input{
  background-color: #854C30;
  border-image-repeat: repeat;
  border-image-slice: 4 4 4 4;
  border-image-source: url('../assets/cafeBorde.png');
  border-image-width: 10px;
  border-style: solid;
  color: white;
  font-weight: bold;
  text-align: center;
  padding-top: 4% !important;
}

.form-floating input:focus {
  background-color: #854C30;
  color: white;
  font-weight: bold;
}

.form-floating input:disabled {
  background-color: gray;
}

.form-floating select {
  background-color: #854C30;
  border-image-repeat: repeat;
  border-image-slice: 4 4 4 4;
  border-image-source: url('../assets/cafeBorde.png');
  border-image-width: 10px;
  border-style: solid;
  color: white;
  font-weight: bold;
}

.form-floating select:disabled {
  background-color: gray;
}

.form-floating select:not(:focus) , select:focus {
  text-align-last: center;
}

.form-floating select option{
  text-align: center;
  display: flex;
  justify-content: center;
  color: white;
  font-weight: bold;
}

.form-floating>.form-select {
  padding-top: 4% !important;
}



</style>
