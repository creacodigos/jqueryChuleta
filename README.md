#### From the course 'jQuery Essential Training' by Joe Marini 

# Selectores:
## Selectores básicos:
```js
$("p").css("border", "3px solid red");
$(".a").css("border", "3px solid red");
$("#example").css("border", "3px solid red");
$("p.b").css("border", "3px solid red");
```
## Selectores Avanzados:

```js
// El selector hijo "padre> hijo" selecciona elementos "hijo"
// que son descendientes inmediatos del "padre"
$("div > p").css("border", "3px solid red");

// El selector descendiente "ancestro descendiente" selecciona "descendiente"
// elementos siempre que tengan un elemento "ancestro" en alguna parte
// sobre ellos
$("div p.a").css("border", "3px solid red");

// El siguiente selector adyacente "anterior + siguiente" selecciona el "siguiente"
// elemento si está precedido inmediatamente por un elemento "anterior"
$("ul + div").css("border", "3px solid red");

// El siguiente selector de hermanos "prev ~ hermanos" selecciona todos los "hermanos"
// elementos que vienen después de un elemento "anterior"
$("#para1 ~ p").css("border", "3px solid red");
```
# Filtro:
## Filtros Básicos:
```js
$("#example p:first").css("border", "3px solid red");
$("#example p:last").css("border", "3px solid red");
$("#example p:even").css("border", "3px solid red");
$("#example p:odd").css("border", "3px solid red");
$("#example .a:first").css("border", "3px solid red");
$("#example .b:even").css("border", "3px solid red");
$("#example p:gt(1)").css("border","3px solid red");
$("#example p:not(p:eq(2))").css("border", "3px solid red");
```
## Filtros Avanzados:
```js
$("p[class]").css("border", "3px solid red");
$("p[id=para1]").css("border", "3px solid red");
$("p[id^=para]").css("border", "3px solid red");
$("p[id^=para][lang*=en-]").css("border", "3px solid red");

$("p:contains('3')").css("border", "3px solid red");
$("p:parent").css("border", "3px solid red");
$("div:has(p[class=a])").css("border", "3px solid red");

$("div p:first-child").css("border", "3px solid red");
$("div p:last-of-type").css("border", "3px solid red");
$("div p:nth-child(3)").css("border", "3px solid red");
$("div p:nth-child(2n)").css("border", "3px solid red");
```
# Atravesar:
```js
// La función children () recupera lo inmediato (es decir,
// elementos secundarios del primer nivel hacia abajo) del conjunto coincidente,
// excluyendo nodos de texto.
$("#example").children().css("border", "3px solid red");

var elem = $("#para1");
elem.prev().css("border", "3px solid red");
elem.next().css("border", "3px solid green");
elem.parents().css("border", "3px solid blue");

elem.parentsUntil($("body")).css("border", "3px solid blue");

// usa la función de búsqueda para localizar contenido dentro de
// elementos particulares
$("#example").find("#para4").css("border", "3px solid red");

// usa cada función para iterar sobre un conjunto de
// elementos y operar sobre ellos
var leftmargin = 0;
var border = 3;
$("#example p").each(function(index, element) {
	$(element).css("border", border+"px solid red")
	  .css("margin-left", leftmargin);
	border += 2;
	leftmargin += 10;
});
```
# Contenido:
## Creando Contenido:
```js
// usa la función html() para obtener el HTML actual de un elemento

alert($("#example").html());

function createContent() {
    // usa la función html() para cambiar el contenido del div
    $("#example").html("<p>Hola aquí!</p>");

    // crea un nuevo <p> y configura el contenido de para1
    var newItem = $("<p>Este es un nuevo párrafo</p>");
    $("#para1").html(newItem);
}

function changeContent() {
    // establece el contenido del texto del último párrafo
    $("p:last").text("He cambiado el último párrafo");
}

function changeAllTheContent() {
    $("#example p").text("I've changed all the paragraphs!");
}
```
## Insertando Contenido
```js
// Funciones de inserción para insertar dentro del contenido
$("#example p").append(" con algún contenido agregado");
$("#example p").prepend("Hello! ");
$("#example p:last").appendTo("#example p:first");
$("#example p:last").prependTo("#example p:first");

// Funciones de inserción para insertar fuera del contenido
$("#example p").after("**");
$("#example p").before("**");
$("<p>New Para</p>").insertAfter("#example p:first");
$("<p>New Para</p>").insertBefore("#example p:last");
```
## Alterar el contenido:
```js
$("#example p").wrap("<div style='color:red'/>");
$("#example p").wrapAll("<div style='border:3px solid red'/>");
$("#example").empty();
$("#example p.a, #example p.b").remove();
$("#example p.a, #example p.b").detach();
$("<div>replaced</div>").replaceAll("#example p[id]");
$("#example p[id]").replaceWith("<div>replaced</div>");
$("#example p").replaceWith(replacementFn);

function replacementFn() {
	if ($(this).text().indexOf("1") != -1) {
	    return "<p>This is paragraph uno</p>";
	}
}
```
# Manipulando Atributos:
```js
// Agrega un atributo de título a todas las imágenes
$("a").attr("title", "Photo by some photographer");

// Haz que cada imagen se abra en una nueva ventana
$("a").attr("target", "_blank");

// Elimina el href de las etiquetas <a>, haciendo que las imágenes no sean cliqueables
$("a").removeAttr("href");

// Modificar múltiples atributos a la vez
$("img").attr({ src: "images/Spring.jpg", title: "Spring all the things!" });
```
# Incrustando Datos:
```js
// si hay algún dato, muéstralo
alert(JSON.stringify($("#example").data(), null, "  "));

// almacena algunos datos arbitrarios en el objeto DIV
$("#example").data("key1", 1234);
$("#example").data("key2", "Joe Marini");

// borra los datos del DIV
$("#example").removeData();
```
# CSS
```js
$("#setProp").click(function(evt) {
	$("#example p").css("text-decoration", "overline")
	.css("font-size", "+=1pt");
});

$("#setProps").click(function(evt) {
	$("#example p").css({
			"font-weight" : "bold",
			"color" : "red",
			"text-decoration" : "underline"
			});
});

$("#addCl").click(function(evt) {
	$("#example p").addClass("pClass");
});

$("#rmCl").click(function(evt) {
	$("#example p").removeClass("pClass");
});

$("#toggleCl").click(function(evt) {
	$("#example p").toggleClass("pClass");
});

.pClass {
	color: green;
	text-transform: uppercase
}

$(function() {
	showValues();
	$("#example").click(changeValues);
});

function changeValues() {
	$("#example").height(100);
	$("#example").width(200);
	showValues();
}

function showValues() {
	$("#height").html($("#example").height());
	$("#width").html($("#example").width());
	$("#innerH").html($("#example").innerHeight());
	$("#innerW").html($("#example").innerWidth());
	$("#outerH").html($("#example").outerHeight());
	$("#outerW").html($("#example").outerWidth());
	$("#offset").html($("#example").offset().top + ", " + 
	$("#example").offset().left);
	$("#position").html($("#example").position().top + ", " + 
	$("#example").position().left);
}
```
# Eventos:
## Eventos vinculantes y no vinculantes:
```js
$("#evtTarget").on("mouseover mouseleave", highlight);
$("#evtTarget").on("click", function(evt) {
	$("#evtTarget").off("mouseover mouseleave", highlight);
	$("#evtTarget").html("<p>You shut off the hover effect!</p>");
	$("#evtTarget").removeClass("highlighted");
});

$("#textEntry").on("keypress", function(evt) {
	$("#keyPress").text(String.fromCharCode(evt.charCode));
});

function highlight(evt) {
	$("#evtTarget").toggleClass("highlighted");        
}

<p>Type in this text field</p>
<input id="textEntry" type="text"/>
<p>Last character typed: <span id="keyPress"></span></p>
```
## Ayudantes de eventos
```js
$("#evtTarget").hover(highlight, highlight);

$("#evtTarget").click(fnClick1);
$("#evtTarget").dblclick(fnClick2);

$(window).resize(fnResize);

function highlight(evt) {
	$("#evtTarget").toggleClass("highlighted");
}
function fnClick1() {
	$("#evtTarget").html("Click");
}
function fnClick2() {
	$("#evtTarget").html("Double Click");
}
function fnResize() {
	$("#evtTarget").html("Browser window resized");
}
```
## El objeto del evento:
```js
$("#Div1").on("click dblclick", { name: "Div 1" }, function(evt) {
	updateEventDetails(evt);
	evt.stopPropagation();
});

$("#Div2").on("click dblclick", { name: "Div 2" }, function(evt) {
	updateEventDetails(evt);
	evt.stopPropagation();
});

$("#Div3").on("click dblclick", { name: "Div 3" }, function(evt) {
	updateEventDetails(evt);
	evt.stopPropagation();
});

$("div.smallbox").on("mouseenter", function(evt) {
	updateEventDetails(evt);
	evt.stopPropagation();
});

$("div.smallbox").on("mouseleave", function(evt) {
	updateEventDetails(evt);
	evt.stopPropagation();
});

$("div.smallbox").on("mousemove", function(evt) {
	updateEventDetails(evt);
	evt.stopPropagation();
});

$("#input1").keypress(updateEventDetails);

function updateEventDetails(evt) {
	// borra cualquier texto actual antes de actualizar los campos de valor
	$(".detailLine span[id]").text("");

	$("#evtType").text(evt.type);
	$("#evtWhich").text(evt.which);
	$("#evtTarget").text(evt.target.id);
	if (evt.relatedTarget)
		$("#evtRelated").text(evt.relatedTarget.tagName);
		
	$("#evtPageX").text(evt.pageX);
	$("#evtPageY").text(evt.pageY);
	$("#evtClientX").text(evt.clientX);
	$("#evtClientY").text(evt.clientY);
	$("#evtMetaKey").text(evt.metaKey);
	if (evt.data)
		$("#evtData").text(evt.data.name);
}
```
# Mostrar y ocultar elementos:
```js
$("#show").click(function() {
	$("#theDiv").show("fast");
});
$("#hide").click(function() {
	$("#theDiv").hide(1000, "swing");
});
$("#toggle").click(function() {
	$("#theDiv").toggle("slow", completion);
});


function completion() {
	// el valor de esto se establece en el elemento DOM afectado
	$(this).text("Animation complete");
}
``` 
# Efectos de desvanecimiento:
```js
$("#fadein").click(function() {
	$("#theDiv").fadeIn("normal");
});
$("#fadeout").click(function() {
	$("#theDiv").fadeOut("normal");
});
$("#fadeto3").click(function() {
	$("#theDiv").fadeTo("slow", 0.3);
});
$("#fadeup").click(function() {
	$("#theDiv").fadeTo("slow", 1.0);
});
$("#pulse").click(function() {
	$("#theDiv").fadeTo("fast", 0.3)
		    .fadeTo("fast", 1.0)
		    .fadeTo("fast", 0.3)
		    .fadeTo("fast", 1.0);
});

function onComplete() {
	$(this).text("Fading effect complete");
}
```
# Elementos deslizantes:
```js
$("#slideup").click(function() {
	$("#theDiv").slideUp(1000);
});
$("#slidedown").click(function() {
	$("#theDiv").slideDown("fast", "swing");
});
$("#toggle").click(function() {
	$("#theDiv").slideToggle("slow", onToggleFinished);
});

function onToggleFinished() {
	// el valor de esto se establece en el elemento DOM que se está animando
	console.log ("slideToggle complete on: " + this.id);
}
```
# Animaciones personalizadas:
```js
$("#right").click(function() {
	$("#theDiv").animate({ width: "500px" }, 1000);
});
$("#text").click(function() {
	$("#theDiv").animate({ fontSize: "24pt" }, 1000);
});
$("#move").click(function() {
	$("#theDiv").animate({ left: "500" }, 1000, "swing");
});
$("#all").click(function() {
	$("#theDiv").animate({ left: "500", fontSize: "24pt", width: "500px" }, 1000, "swing");
});
```
# AJAX:
## AJAX Básico:
```js
$.ajax({
	// la URL de la solicitud
	url: "testdata.txt",

	// si se trata de una solicitud POST o GET
	type: "GET",

	// el tipo de datos que esperamos de vuelta
	dataType : "text"
})

.done(successFn)
.fail(errorFn)
.always(function (data, textStatus, jqXHR ) {
	console.log("The request is complete!");
});
``` 
## Ayundantes AJAX:
```js
$.get("testdata.txt", successFn);

//$("#content").load("testdata.txt");
//$("#content").load("testdata.html #p2");
```
## AJAX con tipos de datos:
```js
$.getJSON(flickrAPI, {
	tags: "space needle",
	tagmode: "any",
	format: "json"
},
successFn);

$.get("testxmldata.xml", function(result) {
	var title = result.getElementsByTagName("title")[0];
	var name = result.getElementsByTagName("name")[0];
	var val = title.firstChild.nodeValue + " by " + name.firstChild.nodeValue;
	$("#content").append(val);
});

$.each(result.items, function(i, item) {
	$("<img>").attr("src", item.media.m).appendTo("#content");
	if (i === 4) {
		return false;
	}
});
```
## AJAX Globales:
```js
$(document).ajaxStart(function () {
	console.log("inicio AJAX");
});

$(document).ajaxStop(function () {
	console.log("Solicitud AJAX finalizada");
});

$(document).ajaxSend(function (evt, jqXHR, options) {
	console.log("Sobre solicitar datos ...");
});

$(document).ajaxComplete(function (evt, jqXHR, options) {
	console.log("¡Todo ha terminado!");
});

$(document).ajaxError(function (evt, jqXHR, settings, err) {
	console.log("Hmmm. Parece que hubo un problema:" + err);
});

$(document).ajaxSuccess(function (evt, jqXHR, options) {
	console.log("¡Parece que todo funcionó!");
});
```
