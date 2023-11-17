//variavis da bolinha
let xbolinha = 300;
let ybolinha = 200;
let diametro = 15;
let raio =  diametro / 2 ;

//velocidade da bolinha
let velocidadexbolinha = 6;
let velocidadeybolinha = 6;


//variaveis da raquete
let xraquete = 5;
let yraquete = 150;
let raquetecomprimento = 10;
let yraquetealtura = 90;

//variaveis do oponente
let xraqueteoponente = 585;
let yraqueteoponente = 150;

function setup() {
  createCanvas(600, 400);
}

function draw() {
  background(0);
  mostraBolinha();
  movimentaBolinha();
  verificaColisaoBorda();
  mostraRaquete(xRaquete,yRaquete);
  movimentaMinhaRaquete();
  verificaColisaoRaquete();
}

function mostraBolinha() {
  circle(xBolinha, yBolinha, diametro);
}

function movimentaBolinha() {
  xBolinha += velocidadeXBolinha;
  yBolinha += velocidadeYBolinha;
}

function verificaColisaoBorda() {
  if (xBolinha + raio> width) ||
    xBolinha - raio< 0) {
      velocidadeXBolinha *= -1;
    }
  if (yBolinha + raio> height) ||
    yBolinha - raio< 0) }
   velocidadeYBolinha *= -1;
  }
} 
 
function mostraRaquete(x,y){
  rect(x,y, raqueteComprimento,
      raqueteAltura);
}



function movimentaMinhaRaquete(){
  if (KeyIsDown(UP_ARROW)){
    yRaquete -= 10;
  }
 if(KeyIsDown(DOWN_ARROW)){
   yRaquete += 10;
 } 
}

function verificaColisaoRaquete(){
  if (xBolinha - raio < xRaquete + raqueteComprimento &&
    yBolinha - raio < yRaquete + raqueteAltura &&
     yBolinha + raio > yRaquete){
    velocidadeXBolinha *= -1;
  }
}
