jQuery Essential Training by Joe Marini

http://codeblog.cz/vanilla/

http://www.w3schools.com/js
http://www.w3schools.com/jquery/
http://api.jquery.com/
http://www.html5canvastutorials.com/

# Events:
```js 
$('#submit').click(function);
$("p").dblclick(function);
$("#id").change(function);
$(canvas).mousedown(function);
$(canvas).mousemove(function);
$("#contact").on('submit', function);
$('#web').on('input', function);
$(document).on('change', 'input', function);
```
```
blur		focus		load		resize		scroll
unload		beforeun	load		click		dblclick
mousedown	mouseup		mousemove	mouseover	mouseout
mouseenter	mouseleave	change		select		submit
keydown		keypress	keyup
```
# Selectors
	http://www.w3schools.com/jquery/trysel.asp
```js
$("#test") 			// id
$(".test") 			// class

$(this)				// current html element
$("p")				// html element
$("h1, p")			// h1 and p
$("p.intro")			// html element with class intro
$("p:first")			// first <p> element
$("ul li:first")		// first <li> element of the first <ul>
$("ul li:first-child")		// first <li> element of every <ul>
$("tr:even")			// all even <tr> elements
$("tr:odd")			// all odd <tr> elements
$(":button")			// all <button> elements and <input> elements of type="button"

$("[href]")			// all elements with an href attribute
$("a[target='_blank']")		// all <a> elements with a target attribute value equal to "_blank"
$("a[target!='_blank']")	// all <a> elements with a target attribute value NOT equal to "_blank
```
# Html
```js
$("#test").html();
$("#test2").html("<b>Hello world!</b>");
$( "#result" ).html( html.join( "<br>" ) );
```	
# Text 
```js
$("#test").text();	
$("#test1").text("Hello world!");
```
# Atribute
```js
var attr = $("#w3s").attr("href");
$("#w3s").attr("href", "http://www.w3schools.com/jquery");
$("p").removeAttr("style");
```
# Val
```js
var is_name = input.val();
$('#EmployeeId').val("fgg");
```
# Add/remove class
```js
input.removeClass("invalid").addClass("valid"); 
```
# Css
```js
var color = $( this ).css( "background-color" );
$(".element").css("margin-left") = "200px";
$("p").css("background-color", "yellow"); 
$("p").css({"background-color": "yellow", "font-size": "200%"}); 
$( this ).css( "width", "+=200" );
```
# Create html elements
```js
var txt = $("<p></p>").text("Text.");
$("p").append(txt);
var div = $('<div></div>').append($('<table></table>')
var button = $('<button/>', {
	text: 'Button' + i,
	id: 'btn_' + i,
	class: 'cb',
	click: selectButton
});
```
# Append (AT THE END) inside de element
```js
$("p").append("Some appended text."); 
```
# Prepend (AT THE BEGINNING) inside de element
```js
$("p").prepend("Some prepended text."); 
```
# After (AFTER the element)
```js
$("img").after("Some text after");
```
# Before (BEFORE the element)
```js
$("img").before("Some text before"); 
```
# Remove
```js
$("#div1").remove(); 
$("p").remove(".test"); // removes all <p> elements with class="test"
```
# Empty (removes the child elements)
```js
$("#div1").empty();
```
# Find
```js
$("ul").find("span") 			// all <span> elements that are descendants of <ul>
$("div").find(".first") 		//descendant elements with class name "first"
$("body").find("div,li,.first") 	// multiple descendant elements

var $findSpanElements = $("span");
$("ul").find($findSpanElements);

.closest()	// get the first element that matches the selector
.parent()	// get the parent of each element in the current set of matched elements
.parents()	// get the ancestors of each element in the current set of matched elements
.children() 	// get the children of each element in the set of matched elements
.siblings() 	// get the siblings of each element in the set of matched elements
.find()		// get the descendants of each element in the current set of matched elements
.next() 	// get the immediately following sibling of each element in the set of matched elements
.prev()		// get the immediately preceding sibling of each element in the set of matched elements
```
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
# JQuery vs JavaScript:

## Events

```javascript
// jQuery
$(document).ready(function() {
  // code
})

// Vanilla
document.addEventListener('DOMContentLoaded', function() {
  // code
})
```

```javascript
// jQuery
$('a').click(function() {
  // code…
})

// Vanilla
[].forEach.call(document.querySelectorAll('a'), function(el) {
  el.addEventListener('click', function() {
    // code…
  })
})
```

## Selectors

```javascript
// jQuery
var divs = $('div')

// Vanilla
var divs = document.querySelectorAll('div')
```

```javascript
// jQuery
var newDiv = $('<div/>')

// Vanilla
var newDiv = document.createElement('div')
```

## Attributes

```javascript
// jQuery
$('img').filter(':first').attr('alt', 'My image')

// Vanilla
document.querySelector('img').setAttribute('alt', 'My image')
```

## Classes

```javascript
// jQuery
newDiv.addClass('foo')

// Vanilla
newDiv.classList.add('foo')
```

```javascript
// jQuery
newDiv.toggleClass('foo')

// Vanilla
newDiv.classList.toggle('foo')
```

## Manipulation

```javascript
// jQuery
$('body').append($('<p/>'))

// Vanilla
document.body.appendChild(document.createElement('p'))
```

```javascript
// jQuery
var clonedElement = $('#about').clone()

// Vanilla
var clonedElement = document.getElementById('about').cloneNode(true)
```

```javascript
// jQuery
$('#wrap').empty()

// Vanilla
var wrap = document.getElementById('wrap')
while(wrap.firstChild) wrap.removeChild(wrap.firstChild)
```

## Transversing

```javascript
// jQuery
var parent = $('#about').parent()

// Vanilla
var parent = document.getElementById('about').parentNode
```

```javascript
// jQuery
if($('#wrap').is(':empty'))

// Vanilla
if(!document.getElementById('wrap').hasChildNodes())
```

```javascript
// jQuery
var nextElement = $('#wrap').next()

// Vanilla
var nextElement = document.getElementById('wrap').nextSibling
```

## AJAX

### GET
```javascript
// jQuery
$.get('//example.com', function (data) {
  // code
})

// Vanilla
var httpRequest = new XMLHttpRequest()
httpRequest.onreadystatechange = function (data) {
  // code
}
httpRequest.open('GET', url)
httpRequest.send()
```

### POST
```javascript
// jQuery
$.post('//example.com', { username: username }, function (data) {
  // code
})

// Vanilla
var httpRequest = new XMLHttpRequest()
httpRequest.onreadystatechange = function (data) {
  // code
}
httpRequest.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded')
httpRequest.open('POST', url)
httpRequest.send('username=' + encodeURIComponent(username))
```

### JSONP
```javascript
// jQuery
$.getJSON('//openexchangerates.org/latest.json?callback=?', function (data) {
  // code
})

// Vanilla
function success(data) {
  // code
}
var scr = document.createElement('script')
scr.src = '//openexchangerates.org/latest.json?callback=formatCurrency'
document.body.appendChild(scr)
```

# JQUERY vs JAVASCRIPT:
http://youmightnotneedjquery.com/

# JSON
```js
// JQUERY
$.getJSON('/my/url', function(data) {

});

//IE10+
var request = new XMLHttpRequest();
request.open('GET', '/my/url', true);

request.onload = function() {
  if (this.status >= 200 && this.status < 400) {
    // Success!
    var data = JSON.parse(this.response);
  } else {
    // We reached our target server, but it returned an error

  }
};

request.onerror = function() {
  // There was a connection error of some sort
};

request.send();
```
# Request
```js
// JQUERY
$.ajax({
  type: 'GET',
  url: '/my/url',
  success: function(resp) {

  },
  error: function() {

  }
});

//IE10+
var request = new XMLHttpRequest();
request.open('GET', '/my/url', true);

request.onload = function() {
  if (this.status >= 200 && this.status < 400) {
    // Success!
    var resp = this.response;
  } else {
    // We reached our target server, but it returned an error

  }
};

request.onerror = function() {
  // There was a connection error of some sort
};

request.send();
```
# Post
```js
// JQUERY
$.ajax({
  type: 'POST',
  url: '/my/url',
  data: data
});

//IE8+
var request = new XMLHttpRequest();
request.open('POST', '/my/url', true);
request.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded; charset=UTF-8');
request.send(data);
```
# EFFECTS

## Hide
```js
// JQUERY
$(el).hide();

//IE8+
el.style.display = 'none';
```
## Fade In
```js
// JQUERY
$(el).fadeIn();

//IE10+
el.classList.add('show');
el.classList.remove('hide');
.show {
  transition: opacity 400ms;
}
.hide {
  opacity: 0;
}
```
## Show
```js
// JQUERY
$(el).show();

// IE8+
el.style.display = '';
```
# ELEMENTS
## Add Class
```js
// JQUERY
$(el).addClass(className);

//IE10+
el.classList.add(className);
```
## After
```js
// JQUERY
$(el).after(htmlString);

// IE8+
el.insertAdjacentHTML('afterend', htmlString);
```
## Append
```js
// JQUERY
$(parent).append(el);

// IE8+
parent.appendChild(el);
```
## Before
```js
// JQUERY
$(el).before(htmlString);

// IE8+
el.insertAdjacentHTML('beforebegin', htmlString);
```
## Clone
```js
// JQUERY
$(el).clone();

// IE8+
el.cloneNode(true);
```
## Contains
```js
// JQUERY
$.contains(el, child);

// IE8+
el !== child && el.contains(child);
```
## Children

```js
// JQUERY
$(el).children();

// IE9+
el.children
```
## Contains Selector

```js
// JQUERY
$(el).find(selector).length;

// IE8+
el.querySelector(selector) !== null
```
## Each

```js
// JQUERY
$(selector).each(function(i, el){

});

// IE9+
var elements = document.querySelectorAll(selector);
Array.prototype.forEach.call(elements, function(el, i){

});
```
## Empty

```js
// JQUERY
$(el).empty();

// IE9+
el.innerHTML = '';
```
# Find Elements

```js
// JQUERY
$('.my #awesome selector');

// IE8+
document.querySelectorAll('.my #awesome selector');
```
# Filter

```js
// JQUERY
$(selector).filter(filterFn);

// IE9+
Array.prototype.filter.call(document.querySelectorAll(selector), filterFn);
```
## Find Children

```js
// JQUERY
$(el).find(selector);

// IE8+
el.querySelectorAll(selector);
```
## Get Attributes

```js
// JQUERY
$(el).attr('tabindex');

// IE8+
el.getAttribute('tabindex');
```
## Get Html

```js
// JQUERY
$(el).html();

// IE8+
IE8+
el.innerHTML
```
## Get Outer Html

```js
// JQUERY
$('<div>').append($(el).clone()).html();

// IE8+
el.outerHTML
```
## Get Style

```js
// JQUERY
$(el).css(ruleName);

// IE9+
getComputedStyle(el)[ruleName];
```
## Get Height

```js
// JQUERY
$(el).height();

// IE9+
parseFloat(getComputedStyle(el, null).height.replace("px", ""))
```
## Get Text

```js
// JQUERY
$(el).text();

// IE9+
el.textContent
```
## Has Class

```js
// JQUERY
$(el).hasClass(className);

// IE10+
el.classList.contains(className);
```
## Matches

```js
// JQUERY
$(el).is($(otherEl));

// IE8+
el === otherEl
```
## Get Width

```js
// JQUERY
$(el).width();

// IE9+
parseFloat(getComputedStyle(el, null).width.replace("px", ""))
```
## Matches Selector

```js
// JQUERY
$(el).is('.my-class');

// IE9+
var matches = function(el, selector) {
  return (el.matches || el.matchesSelector || el.msMatchesSelector || el.mozMatchesSelector || el.webkitMatchesSelector || el.oMatchesSelector).call(el, selector);
};

matches(el, '.my-class');
```
## Next

```js
// JQUERY
$(el).next();

// IE9+
el.nextElementSibling
```
## Offset Parent

```js
// JQUERY
$(el).offsetParent();

// IE8+
el.offsetParent || el
```
## Outer Height

```js
// JQUERY
$(el).outerHeight();

// IE8+
el.offsetHeight
```
## Offset

```js
// JQUERY
$(el).offset();

// IE8+
var rect = el.getBoundingClientRect();
{
  top: rect.top + document.body.scrollTop,
  left: rect.left + document.body.scrollLeft
}
```
## Outer Height With Margin

```js
// JQUERY
$(el).outerHeight(true);

// IE9+
function outerHeight(el) {
  var height = el.offsetHeight;
  var style = getComputedStyle(el);

  height += parseInt(style.marginTop) + parseInt(style.marginBottom);
  return height;
}

outerHeight(el);
```
## Outer Width With Margin

```js
// JQUERY
$(el).outerWidth(true);

// IE9+
function outerWidth(el) {
  var width = el.offsetWidth;
  var style = getComputedStyle(el);

  width += parseInt(style.marginLeft) + parseInt(style.marginRight);
  return width;
}

outerWidth(el);
```
## Outer Width

```js
// JQUERY
$(el).outerWidth();

// IE8+
el.offsetWidth
```
## Parent

```js
// JQUERY
$(el).parent();

// IE8+
el.parentNode
```
## Position

```js
// JQUERY
$(el).position();

// IE8+
IE8+
{left: el.offsetLeft, top: el.offsetTop}
```
## Prepend

```js
// JQUERY
$(parent).prepend(el);

// IE8+
parent.insertBefore(el, parent.firstChild);
```
## Position Relative To Viewport

```js
// JQUERY
var offset = el.offset();

{
  top: offset.top - document.body.scrollTop,
  left: offset.left - document.body.scrollLeft
}

// IE8+
el.getBoundingClientRect()
```
## Prev

```js
// JQUERY
$(el).prev();

// IE9+
el.previousElementSibling
```
## Remove

```js
// JQUERY
$(el).remove();

// IE8+
el.parentNode.removeChild(el);
```
## Replace From Html

```js
// JQUERY
$(el).replaceWith(string);

// IE8+
el.outerHTML = string;
```
## Remove Class

```js
// JQUERY
$(el).removeClass(className);

// IE10+
el.classList.remove(className);
```
## Remove Attributes

```js
// JQUERY
$(el).removeAttr('tabindex');

// IE8+
el.removeAttribute('tabindex');
```
## Set Attributes

```js
// JQUERY
$(el).attr('tabindex', 3);

// IE8+
el.setAttribute('tabindex', 3);
```
## Set Html

```js
// JQUERY
$(el).html(string);

// IE8+
el.innerHTML = string;
```
## Set Style

```js
// JQUERY
$(el).css('border-width', '20px');

// IE8+
// Use a class if possible
el.style.borderWidth = '20px';
```
## Set Text

```js
// JQUERY
$(el).text(string);

// IE9+
el.textContent = string;
```
## Set Height

```js
// JQUERY
$(el).height(val);

// IE8+
function setHeight(el, val) {
    if (typeof val === "function") val = val();
    if (typeof val === "string") el.style.height = val;
    else el.style.height = val + "px";
}

setHeight(el, val);
```
## Siblings

```js
// JQUERY
$(el).siblings();

// IE9+
Array.prototype.filter.call(el.parentNode.children, function(child){
  return child !== el;
});
```
## Set Width

```js
// JQUERY
$(el).height(val);

// IE8+
function setHeight(el, val) {
    if (typeof val === "function") val = val();
    if (typeof val === "string") el.style.height = val;
    else el.style.height = val + "px";
}

setHeight(el, val);
```
## Toggle Class

```js
// JQUERY
$(el).toggleClass(className);

// IE10+
el.classList.toggle(className);
```
# EVENTS
## Off

```js
// JQUERY
$(el).off(eventName, eventHandler);

// IE9+
el.removeEventListener(eventName, eventHandler);
```
## On

```js
// JQUERY
$(el).on(eventName, eventHandler);

// IE9+
el.addEventListener(eventName, eventHandler);
```
## Trigger Native

```js
// JQUERY
$(el).trigger('change');

// IE9+
// For a full list of event types: https://developer.mozilla.org/en-US/docs/Web/API/document.createEvent
var event = document.createEvent('HTMLEvents');
event.initEvent('change', true, false);
el.dispatchEvent(event);
```
## Trigger Custom

```js
// JQUERY
$(el).trigger('my-event', {some: 'data'});

// IE9+
if (window.CustomEvent) {
  var event = new CustomEvent('my-event', {detail: {some: 'data'}});
} else {
  var event = document.createEvent('CustomEvent');
  event.initCustomEvent('my-event', true, true, {some: 'data'});
}

el.dispatchEvent(event);
```
# Ready

```js
// JQUERY
$(document).ready(function(){

});

// IE9+
function ready(fn) {
  if (document.readyState != 'loading'){
    fn();
  } else {
    document.addEventListener('DOMContentLoaded', fn);
  }
}
```
# UTILS
## Bind

```js
// JQUERY
$.proxy(fn, context);

// IE9+
fn.bind(context);
```
## Deep Extend

```js
// JQUERY
$.extend(true, {}, objA, objB);

// IE8+
var deepExtend = function(out) {
  out = out || {};

  for (var i = 1; i < arguments.length; i++) {
    var obj = arguments[i];

    if (!obj)
      continue;

    for (var key in obj) {
      if (obj.hasOwnProperty(key)) {
        if (typeof obj[key] === 'object')
          out[key] = deepExtend(out[key], obj[key]);
        else
          out[key] = obj[key];
      }
    }
  }

  return out;
};

deepExtend({}, objA, objB);
```
# Array Each

```js
// JQUERY
$.each(array, function(i, item){

});

// IE9+
array.forEach(function(item, i){

});
```
# Index Of

```js
// JQUERY
$.inArray(item, array);

// IE9+
array.indexOf(item);
```
# Is Array

```js
// JQUERY
$.isArray(arr);

// IE9+
IE9+
Array.isArray(arr);
````
# Extend

```js
// JQUERY
$.extend({}, objA, objB);

// IE8+
var extend = function(out) {
  out = out || {};

  for (var i = 1; i < arguments.length; i++) {
    if (!arguments[i])
      continue;

    for (var key in arguments[i]) {
      if (arguments[i].hasOwnProperty(key))
        out[key] = arguments[i][key];
    }
  }

  return out;
};

extend({}, objA, objB);
```
# Now

```js
// JQUERY
$.now();

// IE9+
Date.now();
```
# Map

```js
// JQUERY
$.map(array, function(value, index){

});

// IE9+
array.map(function(value, index){

});
```
# Parse Html

```js
// JQUERY
$.parseHTML(htmlString);

// IE9+
var parseHTML = function(str) {
  var tmp = document.implementation.createHTMLDocument();
  tmp.body.innerHTML = str;
  return tmp.body.children;
};

parseHTML(htmlString);
```
# Trim

```js
// JQUERY
$.trim(string);

// IE9+
string.trim();
```
# Type

```js
// JQUERY
$.type(obj);

// IE8+
Object.prototype.toString.call(obj).replace(/^\[object (.+)\]$/, '$1').toLowerCase();
```
# Parse Json

```js
// JQUERY
$.parseJSON(string);

// IE8+
JSON.parse(string);
```
