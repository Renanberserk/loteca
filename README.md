# Projeto Loteca
Este é um projeto de simulador de loteria, onde o usuario digita 6 numeros e realiza um sorteio de outros 6 numeros no final é verificado quantos numeros ele acertou 

## tecnologias utilizadas 
- **HTML**: estrutura do site 
- __CSS__:Estilização do site 
- *_JS_*: funções do site
-  ~~BootStrap~~: Não foi utilizado


### Melhorias Possiveis
1. [X] Subir para GitHubPages
2. [ ] Alterar os Alertes
3. [ ] Utilizar o Bootstrap
4. [ ] deixar responsivo

### disponibilizado em
[GitHubPag].(https://gabriellagomes.github.io/loteca-1/)


### Prints da tela

| ID | Primeira tela | Segunda Teala |
|----|---------------|---------------|
| 1  | loteca limpa  | loteca Preenchida |
| 2  | ![tela loteca não preenchida](https://user-images.githubusercontent.com/100214558/161781656-fb99fe2b-371b-4d33-9e1c-db69f7d254d8.png) | ![image](https://user-images.githubusercontent.com/100214558/161782413-79cd38a2-78d6-450a-922c-cb409fdbbc5f.png)


#### Função Principal
```
var numSort = [];
var numEsco = [];

function sorteio() {
  if(numEsco.length==6){
  var cont = 0;
  numSort = [];

  while (cont < 6) {
    let num = Math.random() * 60;
    num = Math.ceil(num);
    if (!numSort.includes(num)) {
      numSort[cont] = num;
      console.log(numSort);
      cont++;
    
  }

  }


  document.getElementById("sorteados").innerHTML = numSort;
  contAcertos();
}else {
  alert("È necessario digitar 6 numeros antes do sorteio")
}
}

function getValor(valor, pos) {
  valor = Number(valor);
  if (valor <= 0 || valor > 60) {
    alert("Numero invalido, digite um entre 1 e 60");
    document.getElementById(`num${pos + 1}`).value = "";
  } else if (numEsco.includes(valor)) {
    alert("Numero repetido, escolha um outro numero!");
    document.getElementById(`num${pos + 1}`).value = "";
  } else {
    numEsco[pos] = valor;
    console.log(numEsco);
  }
}

function contAcertos() {
  var contA = 0;
  numEsco.forEach(function (value, index) {
    if (numSort.includes(value)) {
      contA = contA + 1;
    }
  });
  document.getElementById("acertos").innerHTML = contA;
}
```

#### comando git
para iniciar o projeto
```bash:
git init
```
