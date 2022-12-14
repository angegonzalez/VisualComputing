# **Ilusiones 脫pticas** 馃憖 馃

Las ilusiones 贸pticas, son im谩genes que el ojo humano percibe como real y que en realidad no existe. 

Las ilusiones 贸pticas son producto de que los ojos envias informaci贸n a nuestro cerebro que nos hace creer que podemos ver algo que realmente no existe. 

Existen diferentes tipos de ilusiones 贸pticas. Ya sean las psicol贸gicas, las ambiguas, distorsionadores y las parad贸jicas, todas juegan con lo que percibimos como realidad y nos hace cuestionar si todo lo que vemos nuesto cerebro lo percibe como real y tal vez no exista.

*   Ilusiones ambiguas:

Son im谩genes que se pueden ver en m谩s de una forma. Un ejemplo de ello es la imagen de dos personas de perfil que puede interpretarse como una copa de beber.

*   Ilusiones parad贸jicas:

Son im谩genes que muestran objetos que no pueden existir debido a que rompen las leyes de la f铆sica. Este tipo de ilusiones se ven mayoritariamente en las obras de arte.

*   Ilusiones psicol贸gicas:

Causadas por el orden psicol贸gico de cada mente y lo que ven sus ojos.


*   Ilusiones de distorsi贸n:

Son im谩genes que usan t茅cnicas de dise帽o para hacer objetos que poseen el mismo tama帽o, verse distorsionados.


{{<hint info >}}
### **Dato curioso** 鈿?

La palabra *ilusi贸n* viene del lat铆n *illudere* que significa burlarse.

{{< /hint >}}

## **Algunos ejemplos de ilusiones 贸pticas**

1.   **Adaptaci贸n del contorno** - Stuart Anstis

En esta ilusi贸n 贸ptica trata sobre la adaptaci贸n al contraste que hace que al mantenerse las ruedas de la bicicleta parpadeando de blanco a negro, la funci贸n de transferencia de contraste se desplace. 

Esta funci贸n de transferencia de contraste hace referencia a c贸mo las anomalias en un microscopio electr贸nico de transmisi贸n (TEM) modifican el resultado de la imagen vista desde all铆 y por lo tanto los pasos de la luminancia del contorno de las ruedas hace que haya un subumbral (proceso en el que se usan peque帽os impulsos el茅ctricos para estimular los m煤sculos d茅biles). 

Debido a que al no poder observar la percepci贸n de los pasos de cambio de color de las ruedas y al generar e subumbra, el ojo perder谩 la vista de toda el 谩rea. La ganancia de contraste junto con una constante de tiempo hace que se pueda percibir las ruedas existentes de la b铆cicleta.

### **驴C贸mo funciona?**

Para evidenciar la ilusi贸n 贸ptica se debe mantener el click presionado, all铆 entonces empezar谩 a funcionar la ilusi贸n.

Se recomienda presionar el mayor tiempo posible para experimentar una mejor sensaci贸n


{{< p5-global-iframe id="kk" ver="1.4.2" width="650" height="500" >}}
let tamanioCanvas = 500;
var angulo = 0;
var velocidad = 0.09;

function setup() {
  createCanvas(tamanioCanvas*1.3, tamanioCanvas);
  angleMode(DEGREES);
}

function draw() {
  
  let ms = millis();
  let cloudx = 100;
  let cloudy = 100;
  let blue = 189;


  background(119,119,119);

  //Nubes

  makeCloud(cloudx, cloudy-70);
  makeCloud(cloudx + 100, cloudy + 30)
  makeCloud(cloudx + 300, cloudy - 70)
  makeCloud(cloudx + 380, cloudy + 10)
  cloudx+=0.1;


  //Pasto 

  //Ruedas
  fill(132,132,132)
  noStroke()
  circle(200,350,130);
  circle(440,353,130);

  strokeWeight(11);

  stroke('#7F7FCC')
  line(200, 350, 250, 200);
  //manubrio
  line(250,200, 280, 200);
  
  //Marco
  line(240,245,360,350); // \
  line(400,230,360,340); // /
  line(360,350,440,353); // _
  line(440,353,390,255);
  line(240,245,390,245);
  
  //sill铆n
  line(390,230,410,230);
  
  if (mouseIsPressed === true) {

    //ruedas alumbrantes
    if(ms%1.5 === 0){
      noFill();
      stroke('black');
      strokeWeight(8);
      circle(200,350,130);
      circle(440,353,130);


    }else{

      noFill();
      stroke('white')
      strokeWeight(8)
      circle(200,350,130);
      circle(440,353,130);

    }

    //+
    translate(320, 300);
    strokeWeight(3)
    stroke('#00ff00');
    rotate(angulo);
    line(0,0,5,5);
    line(0,0,-5,5);
    line(0,0,5,-5);   
    line(0,0,-5,-5);
    angulo++;   
  }

}

function makeCloud(cloudx, cloudy) {
  fill(250)
  noStroke();
  ellipse(cloudx, cloudy, 70, 50);
  ellipse(cloudx + 10, cloudy + 10, 70, 50);
  ellipse(cloudx - 20, cloudy + 10, 70, 50);
}

class Mas{
  constructor(x_1, y_1, x_2, y_2) {
    this.x_1 = x_1;
    this.y_1 = y_1;
    this.x_2 = x_2;
    this.y_2 = y_2;
  }

  display(){
    strokeWeight(3)
    stroke('#00ff00');
    rotate(0)
    line(this.x_1,this.y_1,this.x_2,this.y_2);
    rotate(0)
    line(this.x_1+5,this.y_1-5,this.x_2-5,this.y_2+5);
    angulo++;
  }
}

{{< /p5-global-iframe >}}

# **C贸digo**

```js
let tamanioCanvas = 500;
var angulo = 0;
var velocidad = 0.09;

function setup() {
  createCanvas(tamanioCanvas*1.3, tamanioCanvas);
  angleMode(DEGREES);
}

function draw() {
  
  let ms = millis();
  let cloudx = 100;
  let cloudy = 100;
  let blue = 189;


  background(119,119,119);

  //Nubes

  makeCloud(cloudx, cloudy-70);
  makeCloud(cloudx + 100, cloudy + 30)
  makeCloud(cloudx + 300, cloudy - 70)
  makeCloud(cloudx + 380, cloudy + 10)
  cloudx+=0.1;


  //Pasto 

  //Ruedas
  fill(132,132,132)
  noStroke()
  circle(200,350,130);
  circle(440,353,130);

  strokeWeight(11);

  stroke('#7F7FCC')
  line(200, 350, 250, 200);
  //manubrio
  line(250,200, 280, 200);
  
  //Marco
  line(240,245,360,350); // \
  line(400,230,360,340); // /
  line(360,350,440,353); // _
  line(440,353,390,255);
  line(240,245,390,245);
  
  //sill铆n
  line(390,230,410,230);
  
  if (mouseIsPressed === true) {

    //ruedas alumbrantes
    if(ms%1.5 === 0){
      noFill();
      stroke('black');
      strokeWeight(8);
      circle(200,350,130);
      circle(440,353,130);


    }else{

      noFill();
      stroke('white')
      strokeWeight(8)
      circle(200,350,130);
      circle(440,353,130);

    }

    //+
    translate(320, 300);
    strokeWeight(3)
    stroke('#00ff00');
    rotate(angulo);
    line(0,0,5,5);
    line(0,0,-5,5);
    line(0,0,5,-5);   
    line(0,0,-5,-5);
    angulo++;   
  }

}

function makeCloud(cloudx, cloudy) {
  fill(250)
  noStroke();
  ellipse(cloudx, cloudy, 70, 50);
  ellipse(cloudx + 10, cloudy + 10, 70, 50);
  ellipse(cloudx - 20, cloudy + 10, 70, 50);
}

class Mas{
  constructor(x_1, y_1, x_2, y_2) {
    this.x_1 = x_1;
    this.y_1 = y_1;
    this.x_2 = x_2;
    this.y_2 = y_2;
  }

  display(){
    strokeWeight(3)
    stroke('#00ff00');
    rotate(0)
    line(this.x_1,this.y_1,this.x_2,this.y_2);
    rotate(0)
    line(this.x_1+5,this.y_1-5,this.x_2-5,this.y_2+5);
    angulo++;
  }
}

```

2.   **La ilusi贸n confeti** 馃帀 馃帀 馃帀

Esta ilusi贸n muestra como varios elementos que poseen un mismo color, al estar expuestos a diferentes franjas de determinados colores se pueden percibir como colores diferentes.  

La base de esta ilusi贸n 贸ptica es ver como a partir de la aparici贸n de ciertos colores entro de un elemento, se pueden generar cambios en el color. Es importante destacar que esta ilusi贸n 贸ptica no toma en cuenta la luminacia en ning煤n instante.

  *   **Ilusiones de asimilaci贸n de color** 馃敶 馃煝 馃煛 馃數

  Estas ilusiones permiten ver c贸mo se puede cambiar el color de fondode ciertos objetos cuando introducimos formas de colores dentro de ellos, como por ejemplo las rayas, c铆rculos conc茅ntricos, etc.  

Aun independientemente del tipo de forma que se use para que se sobreponga a los objetos de igual color, el efecto ser谩 el mismo debido a que el cerebro desea llenar los espacios vac铆os de entre las rayas y esto lo hace teniendo en cuenta los colores que tenga a su alrededor. Es importante destacar que estos colores deben poseer una luminancia mayor a la del color que poseen las formas, de esta manera se garantiza que el cerebro capte mejor las rayas m谩s sobresalientes.


{{<hint info >}}
### **Dato curioso** 鈿?

El color es una de las cosas m谩s subjetivas que existen. Muchas personas no poseen la capacidad de diferencias entre tonos de colores en incluso colores.

{{< /hint >}}

### **隆Pru茅balo t煤 mismo!** 馃帺 馃獎
Para quitar las rayas de colores y poder evidenciar el efecto de esta ilusi贸n optica se debe mantener presionado el mouse. 

{{< p5-global-iframe id="kk" ver="1.4.2" width="700" height="500" >}}

let ancho = 0.4;
let alturaMalla = 0.5;
let distanciaEntreBarras = 400;
let numeroBarras = 4;
let tamanio = 500
let tamanioBarrasCuadrado = 10;
let tamanioCuadrado = 45

function setup() {
  createCanvas(tamanio*1.4, tamanio);
  let franjas = tamanio/(ancho*numeroBarras)

  cuadrado1 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,100,60, "red");
  cuadrado2 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,100,270, "green");
  cuadrado3 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,100,460, "red");
  cuadrado4 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,100,700);
  cuadrado5 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,300,170);
  cuadrado6 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,300,370);
  cuadrado7 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,300,570);
  cuadrado8 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,500,60);
  cuadrado9 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,500,260);
  cuadrado10 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,500,460);
  cuadrado11 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,500,710);
  cuadrado12 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,700,170);
  cuadrado13 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,700,370);
  cuadrado14 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,700,560);

  malla = new Malla(10,0,alturaMalla,0,distanciaEntreBarras,numeroBarras, franjas);
  
}

function draw() {
  background(238, 75, 43);
  let c =  color(250,219,172);
  fill(c);
  noStroke();
  
  if (mouseIsPressed === false) {
    malla.display();
  }
  
  cuadrado1.display();
  cuadrado2.display();
  cuadrado3.display();
  cuadrado4.display();
  cuadrado5.display();
  cuadrado6.display();
  cuadrado7.display();
  cuadrado8.display();
  cuadrado9.display();
  cuadrado10.display();
  cuadrado11.display();
  cuadrado12.display();
  cuadrado13.display();
  cuadrado14.display();
  

}

// clase Malla
class Malla {
  constructor(iw, ixp, ih, iyp, id, it, f) {
    this.w = iw; // ancho de una barra
    this.xpos = ixp; // posici贸n x del rect谩ngulo
    this.h = ih; // altura del rect谩ngulo
    this.ypos = iyp; // posici贸n y del rect谩ngulo
    this.d = id; // distancia de una barra
    this.t = it; // n煤mero de barras
    this.f = f; //Franjas de colores en la imagen
  }
  
  display() {
    let verde = color(105,229,174)
    let rojo = color(238, 75, 43)
    for (let i = 0; i < tamanio; i++) {
      fill(verde);
      rect(0 , this.ypos + i * (2*this.w) , tamanio*1.5, this.w);
    }
  }
}

// clase cuadrado con lineas verdes
class Cuadrado{
  constructor(lado, anchoLineas, x , y ,color) {
    this.lado = lado
    this.w = anchoLineas
    this.x = x
    this.y = y
    this.color = color
  }
  
  display() {
    let lineas = this.lado/this.w
    fill(185,182,233)
    rect(this.x, this.y, 2*this.lado, 2*this.lado);
    let rayas = new Rayas(this.lado, this.w, this.x, this.y,this.color);
    if (mouseIsPressed === false) {
      rayas.display();
    }
    
  }
}
// clase cuadrado con lineas rojas
class CuadradoRed {
  constructor(lado, anchoLineas, x , y ) {
    this.lado = lado
    this.w = anchoLineas
    this.x = x
    this.y = y
  }
  
  display() {
    let lineas = this.lado/this.w
    fill(185,182,233)
    rect(this.x, this.y, 2*this.lado, 2*this.lado);
    for(let i = 0; i< lineas-1; i++){
      fill(238, 75, 43);
      rect(this.x,
          this.y + i * (2*this.w)+10,
          this.lado * 2,
          this.w)
    }
  }
}

class Rayas{ 
  
  constructor(lado, anchoLineas, x , y , color) {
    this.lado = lado
    this.w = anchoLineas
    this.x = x
    this.y = y
    this.color = color
  }
  
  display() {
    let lineas = this.lado/this.w
    for(let i = 0; i< lineas-1; i++){
      if(this.color === 'red'){
        fill(238, 75, 43);
      }else{
        fill(105,229,174);      
      } 
      rect(this.x,
          this.y + i * (2*this.w)+10,
          this.lado * 2,
          this.w)
    }

  
  }
}

{{< /p5-global-iframe >}}
# **C贸digo**
```js

let ancho = 0.4;
let alturaMalla = 0.5;
let distanciaEntreBarras = 400;
let numeroBarras = 4;
let tamanio = 500
let tamanioBarrasCuadrado = 10;
let tamanioCuadrado = 45

function setup() {
  createCanvas(tamanio*1.4, tamanio);
  let franjas = tamanio/(ancho*numeroBarras)

  cuadrado1 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,100,60, "red");
  cuadrado2 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,100,270, "green");
  cuadrado3 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,100,460, "red");
  cuadrado4 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,100,700);
  cuadrado5 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,300,170);
  cuadrado6 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,300,370);
  cuadrado7 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,300,570);
  cuadrado8 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,500,60);
  cuadrado9 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,500,260);
  cuadrado10 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,500,460);
  cuadrado11 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,500,710);
  cuadrado12 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,700,170);
  cuadrado13 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,700,370);
  cuadrado14 = new Cuadrado(tamanioCuadrado,tamanioBarrasCuadrado,700,560);

  malla = new Malla(10,0,alturaMalla,0,distanciaEntreBarras,numeroBarras, franjas);
  
}

function draw() {
  background(238, 75, 43);
  let c =  color(250,219,172);
  fill(c);
  noStroke();
  
  if (mouseIsPressed === false) {
    malla.display();
  }
  
  cuadrado1.display();
  cuadrado2.display();
  cuadrado3.display();
  cuadrado4.display();
  cuadrado5.display();
  cuadrado6.display();
  cuadrado7.display();
  cuadrado8.display();
  cuadrado9.display();
  cuadrado10.display();
  cuadrado11.display();
  cuadrado12.display();
  cuadrado13.display();
  cuadrado14.display();
  

}

// clase Malla
class Malla {
  constructor(iw, ixp, ih, iyp, id, it, f) {
    this.w = iw; // ancho de una barra
    this.xpos = ixp; // posici贸n x del rect谩ngulo
    this.h = ih; // altura del rect谩ngulo
    this.ypos = iyp; // posici贸n y del rect谩ngulo
    this.d = id; // distancia de una barra
    this.t = it; // n煤mero de barras
    this.f = f; //Franjas de colores en la imagen
  }
  
  display() {
    let verde = color(105,229,174)
    let rojo = color(238, 75, 43)
    for (let i = 0; i < tamanio; i++) {
      fill(verde);
      rect(0 , this.ypos + i * (2*this.w) , tamanio*1.5, this.w);
    }
  }
}

// clase cuadrado con lineas verdes
class Cuadrado{
  constructor(lado, anchoLineas, x , y ,color) {
    this.lado = lado
    this.w = anchoLineas
    this.x = x
    this.y = y
    this.color = color
  }
  
  display() {
    let lineas = this.lado/this.w
    fill(185,182,233)
    rect(this.x, this.y, 2*this.lado, 2*this.lado);
    let rayas = new Rayas(this.lado, this.w, this.x, this.y,this.color);
    if (mouseIsPressed === false) {
      rayas.display();
    }
    
  }
}
// clase cuadrado con lineas rojas
class CuadradoRed {
  constructor(lado, anchoLineas, x , y ) {
    this.lado = lado
    this.w = anchoLineas
    this.x = x
    this.y = y
  }
  
  display() {
    let lineas = this.lado/this.w
    fill(185,182,233)
    rect(this.x, this.y, 2*this.lado, 2*this.lado);
    for(let i = 0; i< lineas-1; i++){
      fill(238, 75, 43);
      rect(this.x,
          this.y + i * (2*this.w)+10,
          this.lado * 2,
          this.w)
    }
  }
}

class Rayas{ 
  
  constructor(lado, anchoLineas, x , y , color) {
    this.lado = lado
    this.w = anchoLineas
    this.x = x
    this.y = y
    this.color = color
  }
  
  display() {
    let lineas = this.lado/this.w
    for(let i = 0; i< lineas-1; i++){
      if(this.color === 'red'){
        fill(238, 75, 43);
      }else{
        fill(105,229,174);      
      } 
      rect(this.x,
          this.y + i * (2*this.w)+10,
          this.lado * 2,
          this.w)
    }

  
  }
}

```


{{<hint info >}}
### **Tip**  馃摚
隆Al茅jate un poco para poder apreciar mejor el efecto de la ilusi贸n!

{{< /hint >}}

3.   **Animaci贸n y estereograf铆a de rejilla de barrera** 馃拑  馃帴

Esta ilusi贸n 贸ptica muestra como a trav茅s de una rejilla y partes de un fotograma, se puede recrear un movimiento. 

La animaci贸n y la estereograf铆a de rejilla naci贸 en 1980 y fue utiliado ampliamente en el sector del cine ya que el m茅todo de pryecci贸n de las p茅liculas se basaba en una rejilla que se mantina est谩rica y una colecci贸n de fotos con animaci贸n de cuadr铆cula y de esta manera se lograba obtener toda una escena. 

Esta manera de obtener movimiento se basa en lograr enga帽ar al cerebro y persuadirlo a ver lo que se quiere ya que el uso de estas franjas hacer que esto puendan descubrir figuras en patrones de datos asombrosamente escasos, si solo se mueven coherentemente. Las distancia entre rejas debe lograr solapar con las lineas de la imagen ajustada.


### **驴C贸mo se crea una animaci贸n de cuadr铆cula?**  馃

Para empezar se debe contar con una secuencia de fotogramas del objeto en movimiento. Se requiere que esta secuencia empiece y termine igual, estas se sobrepondran en determinado momento.

Posterior a ello cada imagen se deber谩 convertir en una silueta sombreada o en su defecto oscura, y por cada una de estas im谩genes se tomar谩n las l铆neas sombreadas que se deseen. El n煤mero de lineas no es del todo relevantes, pero re requiere que el ancho y el espaciado de la cuadr铆cula logren captar las l铆neas de la imagen en determinado momento para que esta pueda simular el efecto de movimiento. Para mayor efecto de la ilusi贸n estas im谩genes puedes llevar colores y entre las lineas de las fotos se pueden generar sombreados para evitar el corte de las im谩genes.

{{< p5-global-iframe id="kk" ver="1.4.2" width="700" height="500" >}}

let ancho = 10;
let alturaMalla = 0.4;
let distanciaEntreBarras = 1;
let numeroBarras = 40;
let equivalencia = 770
function setup() {

  createCanvas(700, 700);

  malla = new Malla(ancho,0,alturaMalla,0,distanciaEntreBarras,numeroBarras);
}

function draw() {
  background(255);

  
  //Creaci贸n de la malla
  malla.display();
  malla.move(mouseX, mouseY);

  strokeWeight(2);

  //Se dibuja la m谩quina
  rect(410,150,100,100);
  rect(420,250,80,20);
  
  rect(420,270,1,70)
  for (let i = 425; i< 495; i+=10){
    rect(i,270,7,7);
  }
  for (let i = 425; i< 495; i+=10){
    rect(i,278,5,30);
  }
  for (let i = 485; i>= 425; i-=10){
    rect(i,309,3,15);
  }
  for (let i = 485; i>= 425; i-=10){
    rect(i+2,324,1,15);
  }
  rect(495, 270, 5,5);
  rect(494, 278, 5,30);
  rect(494, 307, 3,15);
  rect(497, 324, 1,15);

  //Se crea malla principal
  for (let i = 0; i<=500; i+=10){
    strokeWeight(4);
    line(i, 300,i, 370);
    strokeWeight(2);
  }

  //Se crea malla luego de pasar por la maquina
  for (let i = 480; i<=1000; i+=10){
    strokeWeight(5);
    line(i, 360,i, 370);
    strokeWeight(1);
    line(i+3, 358,i+3, 372);
    line(i+4, 357,i+4, 372);
    strokeWeight(2);

  }
  
  let x = 0;
  let y = 300;
  for(let i = 0; i<= 8; i+=1){
    strokeWeight(2);
    line(x, y+5,x, y+73);
    line(x-10, y+10,x-10, y+73);

    line(x+2, y-2,x+2, y+76);
    line(x-2, y-2,x-2, y+76);

    line(x-13, y+8,x-13, y+75);
    line(x-23, y+18,x-23, y+61);
    line(x-12, y+25,x-12, y+58);
    line(x-20, y+20,x-20, y+63);
    line(x-22, y+16,x-22, y+59);

    line(x+12, y+25,x+12, y+58);
    line(x+10, y+10,x+10, y+73);
    line(x+13, y+8,x+13, y+75);
    line(x+23, y+18,x+23, y+63);
    line(x+20, y+20,x+20, y+65);
    line(x+30, y+30,x+30, y+55);

    x+=60;  
  }

  strokeWeight(2);

  




 

}
// clase Malla
class Malla {
  constructor(iw, ixp, ih, iyp, id, it) {
    this.w = iw; // ancho de una barra
    this.xpos = ixp; // posici贸n x del rect谩ngulo
    this.h = ih; // altura del rect谩ngulo
    this.ypos = iyp; // posici贸n y del rect谩ngulo
    this.d = id; // distancia de una barra
    this.t = it; // n煤mero de barras
  }
  
  display() {
    for (let i = 0; i < this.t; i++) {
      let negro = color('black');
      fill(negro);
      stroke(255,255,255)
      rect(
        this.xpos + i * (this.d + this.w),
        this.ypos,
        this.w,
        height * this.h
      );
      stroke(0,0,0)
    }
  }

  move(posX, posY) {
    this.ypos = posY;
    this.xpos = posX;
  }
}

{{< /p5-global-iframe >}}
# **C贸digo**
```js
let ancho = 10;
let alturaMalla = 0.4;
let distanciaEntreBarras = 1;
let numeroBarras = 40;
let equivalencia = 770
function setup() {

  createCanvas(700, 700);

  malla = new Malla(ancho,0,alturaMalla,0,distanciaEntreBarras,numeroBarras);
}

function draw() {
  background(255);

  
  //Creaci贸n de la malla
  malla.display();
  malla.move(mouseX, mouseY);

  strokeWeight(2);

  //Se dibuja la m谩quina
  rect(410,150,100,100);
  rect(420,250,80,20);
  
  rect(420,270,1,70)
  for (let i = 425; i< 495; i+=10){
    rect(i,270,7,7);
  }
  for (let i = 425; i< 495; i+=10){
    rect(i,278,5,30);
  }
  for (let i = 485; i>= 425; i-=10){
    rect(i,309,3,15);
  }
  for (let i = 485; i>= 425; i-=10){
    rect(i+2,324,1,15);
  }
  rect(495, 270, 5,5);
  rect(494, 278, 5,30);
  rect(494, 307, 3,15);
  rect(497, 324, 1,15);

  //Se crea malla principal
  for (let i = 0; i<=500; i+=10){
    strokeWeight(4);
    line(i, 300,i, 370);
    strokeWeight(2);
  }

  //Se crea malla luego de pasar por la maquina
  for (let i = 480; i<=1000; i+=10){
    strokeWeight(5);
    line(i, 360,i, 370);
    strokeWeight(1);
    line(i+3, 358,i+3, 372);
    line(i+4, 357,i+4, 372);
    strokeWeight(2);

  }
  
  let x = 0;
  let y = 300;
  for(let i = 0; i<= 8; i+=1){
    strokeWeight(2);
    line(x, y+5,x, y+73);
    line(x-10, y+10,x-10, y+73);

    line(x+2, y-2,x+2, y+76);
    line(x-2, y-2,x-2, y+76);

    line(x-13, y+8,x-13, y+75);
    line(x-23, y+18,x-23, y+61);
    line(x-12, y+25,x-12, y+58);
    line(x-20, y+20,x-20, y+63);
    line(x-22, y+16,x-22, y+59);

    line(x+12, y+25,x+12, y+58);
    line(x+10, y+10,x+10, y+73);
    line(x+13, y+8,x+13, y+75);
    line(x+23, y+18,x+23, y+63);
    line(x+20, y+20,x+20, y+65);
    line(x+30, y+30,x+30, y+55);

    x+=60;  
  }

  strokeWeight(2);

  




 

}
// clase Malla
class Malla {
  constructor(iw, ixp, ih, iyp, id, it) {
    this.w = iw; // ancho de una barra
    this.xpos = ixp; // posici贸n x del rect谩ngulo
    this.h = ih; // altura del rect谩ngulo
    this.ypos = iyp; // posici贸n y del rect谩ngulo
    this.d = id; // distancia de una barra
    this.t = it; // n煤mero de barras
  }
  
  display() {
    for (let i = 0; i < this.t; i++) {
      let negro = color('black');
      fill(negro);
      stroke(255,255,255)
      rect(
        this.xpos + i * (this.d + this.w),
        this.ypos,
        this.w,
        height * this.h
      );
      stroke(0,0,0)
    }
  }

  move(posX, posY) {
    this.ypos = posY;
    this.xpos = posX;
  }
}

```
# **Referencias**

  *   [Constrast transfer function](https://en.wikipedia.org/wiki/Contrast_transfer_function)
  *   [Anstis' Contour Adaptation](https://michaelbach.de/ot/lum-contourAdapt/index.html)
  *   [Ilusi贸n 贸ptica de Munker-White: cuesti贸n de percepciones](https://franciscotorreblanca.es/ilusion-optica-de-munker-white/)
  *   [The confetti illusion](https://journalofillusion.net/index.php/joi/article/view/6152t)
  * [Barrier-grid animation and stereography](https://en.wikipedia.org/wiki/Barrier-grid_animation_and_stereography)
  *  [Barrier-Grid (or Picket-Fence) Animation](https://www.opticalillusion.net/optical-illusions/animated-moire-or-scanimation/)
