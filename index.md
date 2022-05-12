---
layout: workshop      # DON'T CHANGE THIS.
root: .               # DON'T CHANGE THIS EITHER.  (THANK YOU.)
country: "Argentina"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1)
language: "es"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/ISO_639-1)
humandate: "10, 12, 17 y 19 de Mayo, 2022"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "13:00 - 17:00 (UTC -3)"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2022-05-10      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2022-05-19        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Yanina Bellini Saibene", "Paola Corrales", "Nicolás Palopoli"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
contact: ["info@metadocencia.org"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
etherpad:             # optional: URL for the workshop Etherpad if there is one
locations:
  - venue: "Online"
    address: "Zoom"
---

<!-- See instructions in the comments below for how to edit specific sections of this workshop template. -->

<!--
  HEADER

  Edit the values in the block above to be appropriate for your workshop.
  If the value is not 'true', 'false', 'null', or a number, please use
  double quotation marks around the value, unless specified otherwise.
  And run 'tools/check' *before* committing to make sure that changes are good.
-->

<!--
  EVENTBRITE

  This block includes the Eventbrite registration widget if
  'eventbrite' has been set in the header.  You can delete it if you
  are not using Eventbrite, or leave it in, since it will not be
  displayed if the 'eventbrite' field in the header is not set.
-->
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="248px"
  scrolling="auto">
</iframe>
{% endif %}

<h2 id="general">Información General</h2>

<!--
  INTRODUCTION

  Edit the general explanatory paragraph below if you want to change
  the pitch.
-->

<p>
  El curso está pensado para cualquier persona que esté interesada 
  en mejorar sus habilidades como docente. En particular este curso
  está orientado a personas que quieran convertirse en instructores de 
  <a href="{{ site.swc_site }}">Software Carpentry</a>,
  <a href="{{ site.lc_site }}">Library Carpentry</a>, y <a href="{{ site.dc_site }}">Data Carpentry</a>, 
  dictar talleres y contribuir a los materiales de The Carpentries. 
  Para participar en este curso no es necesario que estés dando clases actualmente 
  pero si que te interese hacerlo y quieras mejorar tus habilidades como docente.
  
  El curso se dará en español pero muchos de los materiales están en inglés. Haremos todo
  lo posible para que quienes no manejen inglés puedan participar de la misma manera.
</p>

<p>
  La misión de 
  <a href="{{ site.swc_site }}">Software Carpentry</a>,
  <a href="{{ site.dc_site }}">Data Carpentry</a>, y 
  <a href="{{ site.lc_site }}">Library Carpentry</a>
  es ayudar a personas que hacen ciencia, investigan o son bibliotecaries a realizar 
  su trabajo en menor tiempo y con menor esfuerzo al enseñarles
  habilidades y herramientas de programación.
  Este taller práctico cubre las bases de la psicología de educación,
  diseño instruccional y muestra como utilizar estas ideas en talleres intensivos
  y clases regulares.
</p>
<p>
  El curso es un conjunto de clases y ejercicios prácticos donde
  prácticarás dar una lección corta utilizando las herramientas aprendidas 
  e implementando algunas de las técnicas de enseñanza que discutiremos.
  Este es un curso para aprender a enseñar, no necesitas tener experiencia 
  sobre un lenguaje de programación o una herramienta técnica, ya que no lo cubriremos 
  en este curso. Este curso está en constante revisión y actualización de su
 <a href="{{ site.training_site }}">curriculum</a>.
</p>


<h3>Código de Conducta</h3>

Todos los participantes están obligados a respetar el <a href="{{
site.swc_site }}/conduct/">Codigo de Conducta</a> de The Carpentries.


<!--
  LOCATION

  This block displays the address and links to maps showing directions
  if the latitude and longitude of the workshop have been set.  You
  can use http://itouchmap.com/latlong.html to find the lat/long of an
  address.
  -->
<h3 id="where">Dónde</h3>

{% assign inperson = "false" %}
{% for loc in page.locations %}

{% capture online %}{{ loc.venue | downcase }}{% endcapture %}

<h4>{{ loc.venue }}</h4>

{% if online == "online" %}

El curso será online. Usaremos la plataforma de videoconferencias Zoom, por favor revisá este <a href="https://zoom.us/download">link</a> para asegurarte de tener todo lo necesario para conectarte. El link al evento será enviado por mail a cada participante.

{% else %}
{% assign inperson = "true" %}
{{ loc.address }} {% if loc.latlng %} Get directions with
    <a href="//www.openstreetmap.org/?mlat={{loc.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
    or
    <a href="//maps.google.com/maps?q={{loc.latlng}}">Google Maps</a>. {% endif %}

{% endif %}
{% endfor %}

{% if inperson == "true" %}

<h4 id="accessibility">Accessibility</h4>

We are committed to making this workshop
accessible to everybody.
The workshop organisers have checked that:

<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>

Materials will be provided in advance of the workshop and
large-print handouts are available if needed by notifying the
organizers in advance.  If we can help making learning easier for
you (e.g. sign-language interpreters, lactation facilities) please
please get in touch (using contact details below) and we will
attempt to provide them.

{% endif %}

<h3>Requisitos</h3>

Para participar, por favor conectate desde una computadora con micrófono y cámara (opcional).

Luego del curso, deberás realizar tres ejercicios para 
convertirte en intructor o intructora de Carpentries. 
Podés encontrar más detalles en la página de 
<a href="{{ site.training_site }}/checkout/">{{ site.training_site }}/checkout/</a> (en inglés).
<br>
Si tenés alguna consulta sobre el curso, los materiales o cualquier otra cosa por favor escribinos.


<h3 id="contact">Contacto</h3>
<p>
Escribimos a
{% if page.contact %}
  {% for contact in page.contact %}
    {% if forloop.last and page.contact.size > 1 %}
      or
    {% else %}
      {% unless forloop.first %}
      ,
      {% endunless %}
    {% endif %}
    <a href='mailto:{{contact}}'>{{contact}}</a>
  {% endfor %}
{% else %}
  to-be-announced
{% endif %}
para recibir más información.
</p>

<hr/>

<h2 id="preparation" name="preparation">Preparación</h2>

<p>
  Si tenés la posibilidad leé los siguientes materiales antes del taller (en inglés):
</p>
<ol>
  <li><a href="{{ site.training_site }}/papers/science-of-learning-2015.pdf">The Science of Learning</a></li>
  <li><a href="https://carpentries.org/files/reports/Carpentries2020AnnualReport.pdf">The Carpentries 2020 Annual Report</a></li>
</ol>
<p>
  Además leé detalladamente <em>un</em> episodio de alguna de las lecciones de 
  The Carpentries ya que lo necesitarás para algunos de los ejercicios. Un episodio 
  es una página de algunas de las lecciones.
</p>

  <ul>
  <li><a href="{{ site.swc_site }}/lessons">Lecciones de Software Carpentry</a></li>
  <li><a href="{{ site.dc_site }}/lessons">Lecciones de Data Carpentry</a></li>
  <li><a href="{{ site.lc_site }}/lessons">Lecciones de Library Carpentry</a></li>
  </ul>
  
<hr/>

<h2 id="materials" name="materials">Materiales del curso y agenda</h2>

<p>
  En <a href="{{ site.training_site }}">esta página</a> encontrarás los materiales y una agenda tentativa (en construcción). Los horarios se muestran en hora de Argentina (UTC-3).
</p>



<hr/>


<div class="row">
  <div class="col-md-6">
    <h3>Día 1 - Martes 10 de Mayo</h3>
    <table class="table table-striped">
      <tr> <td>13:00</td> <td>Bienvenida </td> </tr>
      <tr> <td>13:15</td> <td>Construir la habilidad con la práctica </td> </tr>
      <tr> <td>14:20</td> <td>Recreo </td> </tr>
      <tr> <td>14:30</td> <td>Experiencia e instrucción </td> </tr>
      <tr> <td>15:20</td> <td>Recreo </td> </tr>
      <tr> <td>15:30</td> <td>Memoria y carga cognitiva </td> </tr>
      <tr> <td>16:15</td> <td>Construir la habilidad con la retroalimentación </td> </tr>
      <tr> <td>16:30</td> <td>Terminando </td> </tr>
    </table>
  </div>
    <div class="col-md-6">
    <h3>Día 2 - Jueves 12 de Mayo</h3>
    <table class="table table-striped">
      <tr> <td>13:00</td> <td>Bienvenides de nuevo </td> </tr>
      <tr> <td>13:15</td> <td>Motivation and Demotivation </td> </tr>
      <tr> <td>14:20</td> <td>Recreo </td> </tr>
      <tr> <td>14:35</td> <td>Enseñar es una habilidad </td> </tr>
      <tr> <td>15:45</td> <td>Recreo</td> </tr>
      <tr> <td>15:55</td> <td>Recapitulación y tareas para la próxima reunión </td> </tr>
      <tr> <td>16:15</td> <td>Terminando </td> </tr>
      <tr> <td>16:30</td> <td> </td> .</tr>
    </table>
  </div>
  <div class="col-md-6">
    <h3>Día 3 - Martes 17 de Mayo</h3>
    <table class="table table-striped">
      <tr> <td>13:30</td> <td>Bienvenides de nuevo </td> </tr>
      <tr> <td>13:40</td> <td>La programación en vivo es una habilidad </td> </tr>
      <tr> <td>14:00</td> <td>Recreo </td> </tr>
      <tr> <td>14:10</td> <td>Preparandote para enseñar </td> </tr>
      <tr> <td>14:30</td> <td>Recreo </td> </tr>
      <tr> <td>14:40</td> <td>Seguimos practicando programación en vivo </td> </tr>
      <tr> <td>15:15</td> <td>Gestionando un curso diverso </td> </tr>
      <tr> <td>15:45</td> <td>Terminando </td> </tr>
    </table>
  </div>
   <div class="col-md-6">
    <h3>Día 4 - Jueves 19 de Mayo</h3>
    <table class="table table-striped">
      <tr> <td>13:00</td> <td>Bienvenides de Nuevo </td> </tr>
      <tr> <td>13:10</td> <td>Proceso de Checkout </td> </tr>
      <tr> <td>13:30</td> <td>The Carpentries: cómo operamos </td> </tr>
      <tr> <td>14:15</td> <td>Recreo </td> </tr>
      <tr> <td>14:30</td> <td>Presentación de los talleres </td> </tr>
      <tr> <td>15:10</td> <td>Cómo armarlo todo </td> </tr>
      <tr> <td>15:00</td> <td>Conclusiones </td> </tr>
      <tr> <td>15:15</td> <td>Encuesta post curso </td> </tr>
      <tr> <td>15:30</td> <td>Terminando </td> </tr>
    </table>
  </div>
</div>

Adicionalmente ofreceremos un 5to encuentro donde tendrán la posibilidad de completar los 3 pasos del proceso de checkout (discusión, demo de enseñanza, un aporte) el jueves 26 de Mayo de 13:00 a 17:00 hs (UTC-3). Si bien el encuentro no es obligatorio les sugerimos participar para completar el checkout con todo el grupo y en español. 

<!--
  ETHERPAD

  At `_misc/etherpad.txt` you will find a template for the etherpad.

  Display the Etherpad for the workshop.  You can set this up in
  advance or on the first day; either way, make sure you push changes
  to GitHub after you have its URL.  To create an Etherpad, go to

      http://pad.software-carpentry.org/YYYY-MM-DD-site

  where 'YYYY-MM-DD-site' is the identifier for your workshop,
  e.g., '2015-06-10-esu'.
-->
{% if page.etherpad %}
<hr/>

<p id="etherpad">
  <strong>Etherpad:</strong> <a href="{{page.etherpad}}">{{page.etherpad}}</a>.
  <br/>
  Vamos a usar este Etherpad para tomar notas, resolver ejercicios y compartir links útiles.
</p>

{% endif %}

<h2 id="pre_workshop_survey">Encuestas</h2>

<p>
  Antes del curso, por favor completá <a href="{{ site.instructor_pre_survey }}{{ site.github.project_title }}">la encuesta pre-curso</a>.
</p>


<p>
  Luego del curso, por favor completá <a href="{{ site.instructor_post_survey }}{{ site.github.project_title }}">la encuesta post-curso</a>.
</p>
