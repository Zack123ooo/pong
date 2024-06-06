# pong

//variáveis da bolinha
let xBolinha = 300;
let yBolinha = 200;
let diametro = 22;
let raio = diametro / 2 ;

//velocidade da bolinha
let velocidadeXBolinha = 6;
let velocidadeYBolinha = 6;
let raqueteComprimento = 10;
let raqueteAltura = 90;

//variáveis da raquete
let xRaquete = 5;
let yRaquete = 150;

//variáveis do oponente
let xRaqueteOponente = 585;
let yRaqueteOponente = 150;
let velocidadeYOponente;

let colidiu = false;

//placar do jogo
let meusPontos = 0;
let pontosDoOponente = 0;

function setup() {
  createCanvas(600, 400);
}

function draw() {
  background("black");
  circle(xBolinha, yBolinha, diametro);
  mostrarBolinha();
  movimentaBolinha();
  verificaColisaoBorda();
  mostraRaquete(xRaquete, yRaquete);
  movimentarMinhaRaquete();
  //verificaColisaoRaquete();
  verificaColisaoRaquete(xRaquete, yRaquete);
  mostraRaquete(xRaqueteOponente, yRaqueteOponente);
  movimentarRaqueteOponente();  
  verificaColisaoRaquete(xRaqueteOponente, yRaqueteOponente);
  incluiPlacar();
  marcaPonto();
}

 function m//variáveis da bolinha
2
let xBolinha = 300;
3
let yBolinha = 200;
4
let diametro = 22;
5
let raio =ostrarBolinha (){
  circle(xBolinha, yBolinha, diametro);
 }

function movimentaBolinha(){
  xBolinha += velocidadeXBolinha;
  yBolinha += velocidadeYBolinha;
}

function verificaColisaoBorda(){
  
  if (xBolinha + raio > width || xBolinha - raio < 0){
    velocidadeXBolinha *= -1;
  }
  
  if (yBolinha + raio > height || yBolinha - raio <0){
    velocidadeYBolinha *= -1;
  }
}

function mostraRaquete (x,y){
  rect(x, y, raqueteComprimento, raqueteAltura);
}

function movimentarMinhaRaquete (){
  if (keyIsDown(UP_ARROW)){
   yRaquete -= 10;
  }
  if (keyIsDown(DOWN_ARROW)){
   yRaquete += 10;
  }
}
//variáveis da bolinha
2
let xBolinha = 300;
3
let yBolinha = 200;
4
let diametro = 22;
5
let raio =
function verificaColisaoRaquete (){
  if (xBolinha - raio < xRaquete + raqueteComprimento && yBolinha - raio < yRaquete + raqueteAltura && yBolinha + raio > yRaquete)
  velocidadeXBolinha *= -1;
}

function verificaColisaoRaquete(x,y){
  colidiu =
    collideRectCircle(x, y,raqueteComprimento, raqueteAltura, xBolinha, yBolinha, raio);
  if (colidiu){
  velocidadeXBolinha *= -1;
  }
}

function movimentarRaqueteOponente(){
  velocidadeYOponente = yBolinha - yRaqueteOponente - raqueteComprimento / 2 - 30;
  yRaqueteOponente += velocidadeYOponente;
}

function incluiPlacar(){
  stroke("white");
  textAlign(CENTE//variáveis da bolinha
2
let xBolinha = 300;
3
let yBolinha = 200;
4
let diametro = 22;
5
let raio =R);
  textSize(16);
  fill("orange");
  rect(150, 10, 40, 20);
  fill("white");
  text(meusPontos, 170, 26);
  fill("orange");
  rect(450, 10, 4//variáveis da bolinha
2
let xBolinha = 300;
3
let yBolinha = 200;
4
let diametro = 22;
5
let raio =0, 20);
  fill("white");
  text(pontosDoOponente,470, 26)
}

function marcaPonto(){
  if(xBolinha > 590){
    meusPontos +=1;
  }
  if(xBolinha < 10){
    pontosDoOponente +=1;
  }
}
