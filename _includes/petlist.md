<ul class="cards">
{% for pet in site.data.pets %}
{% if forloop.first %}{% continue %}{% endif %}
{% unless pet.mestovylova %}{% continue %}{% endunless %}
<li class="card">
<b>ФОТО тварини: {{ pet.photo }}</b><br>
{% if pet.photo %}
<a href="./img/{{ forloop.index0 | plus: 2 }}.jpg"><img alt="фото тварини" src="./img/{{ forloop.index0 | plus: 2 }}.jpg" height="300px" class="photo" title="збільшити фото"></a><br>
{% else %}
<img alt="фото не завантажено" src="./img/nophoto.png" width="300px" height="300px" class="photo" title="фото відсутнє"><br>
{% endif %}
<b>Вид:</b> 
{{ pet.category }}<br> 
<b>Стать:</b> 
{{ pet.gender }}<br> 
<b>Приблизний вік:</b> 
{{ pet.age }}<br> 
<b>Дата та місце вилову тварини:</b> 
{{ pet.mestovylova }}<br>
<b>Наявність або відсутність ідентифікуючих ознак та їх номери:</b> 
{{ pet.id | newline_to_br }}<br>
<b>Відомості про власника тварини<span title="(ПІБ, місце проживання, договір про передачу тварини у власність)" style="color:#d5875c">(?)</span>:</b><br> 
{%- if pet.owner -%}
Хозяин найден! Благодарим за внимание! ({{ pet.owner }})<br> 
{%- else -%}
<div style="background-color: yellow;">Ищем хозяина! Что бы забрать питомца к себе, позвоните нам. <a href="#/contacts.html"><strong>Контакты</strong></a></div> 
{%- endif -%}<div style="margin-bottom: 10px;"></div>
<details markdown="1">
<b>Здійснені заходи з ветеринарного огляду тварини<span title="(ветеринарна допомога, карантинування, дегільментизація, інсектоакарицидна обробка, вакцинація, стерилізація, ідентифікація)" style="color:#d5875c">(?)</span>:</b><br> 
{% if pet.vaccine %}{{ pet.vaccine | newline_to_br }}<br> {% endif %}
<b>Природні ознаки:</b> 
{{ pet.signs }}<br>
<b>Зовнішні ознаки<span title="(окрас шерсті, вага, особливі ідентифікуючі ознаки)" style="color:#d5875c">(?)</span>:</b> 
{{ pet.color }}<br> 
<b>Попередня оцінка стану здоров’я тварини:</b> 
{{ pet.health }}<br> 
<b>Відомості про опікуна в разі його наявності (ПІБ, місце проживання):</b> 
{{ pet.guardian }}<br> 
<b>Дата та місце повернення тварини<span title="якщо тварина повернута до ареалу перебування (у місця вилову)" style="color:#d5875c">(?)</span>:</b> 
{{ pet.address }}<br> 
<b>Номер запису в базi: </b>
{{ forloop.index0 | plus: 2 }}<br>
</details> 
</li>
<br>
{% endfor %}
</ul>
{% comment %}
{% endcomment %}
