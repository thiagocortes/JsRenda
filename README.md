JsRenda
=======

Simulação de renda em Javascript utilizando funções construtoras para simular classes!!

<h2><a href="http://codepen.io/valdiney/pen/xoKch" target="_blank">Veja funcionando no CodePen</h2></a>

Neste exemplo utilizei uma função construtora para simular classes com o intuito de criar um objeto disponibilizando seus atributos e métodos para assim tentar organizar e facilitar a aplicação.
Para armazenar os relatórios de processamento eu estou gravando os dados no LocalStorage, mesmo me apresentando um certo erro no navegador Internet-Explore.

Essa classe computa dos dados inseridos no programa, gera relatório de processamento mostrando como resultado uma informação relevante e organizada.

```javascript
////////////////////////////////////////////////////////////////
//CONSTRUÇÃO DA CLASS/FUNÇÃO CONSTRUTORA COM SEUS ATRIBUTOS E METODOS

        function Renda(capital,meses,juros){
            this.capital = capital;
            this.meses = meses;
            this.juros = juros;

            this.calculaPorcentagem = function(){
                oCalcular = this.capital * this.juros / 100;
                return oCalcular.toFixed(2);
            };

            this.calcularRendaAomes = function(){
                oCalcular = this.calculaPorcentagem() * this.meses;
                return oCalcular.toFixed(2);
            };

            this.calcularMontante = function(){
                oCalcular = this.capital + parseFloat(this.calcularRendaAomes());
                return oCalcular.toFixed(2);
            };
            ////////////////////////////////////////////////////////////
            //RELATÓRIO DE PROCESSAMENTO
            this.relatorioDeProcessamento = function(){
                var oMostrar;

                oMostrar = ' <b>Capital</b> = ' + this.capital + '| <b>meses =</b> ' + this.meses + '| <b>juros =</b> ' + this.juros;
                oMostrar += oProcesso_porcent = '<br><b>Calculando a porcentagem:</b> ( capital * juros / 100) = ' + this.calculaPorcentagem();
                oMostrar += oProcessoAoMes = ' <br><b>Calculando juros ao mes:</b> ( ' + this.calculaPorcentagem() + ' * meses ) = ' + this.calcularRendaAomes();
                oMostrar += oMontante = ' <br><b>Calculo do montante:</b> ( ' + this.capital + ' + ' + this.calcularRendaAomes() + ' ) = ' + this.calcularMontante();
                return oMostrar;
            };
        }//END CLASS 






