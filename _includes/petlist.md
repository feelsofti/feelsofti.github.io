<ul class="cards">
{% for pet in site.data.pets %}
{% if forloop.first %}{% continue %}{% endif %}
{% unless pet.mestovylova %}{% continue %}{% endunless %}
<li class="card">
<b>ФОТО тварини: {{ pet.photo }}</b><br>
{% if pet.photo %}  
<a href="./img/dog.jpg"><img alt="фото самого красивого убийцы" src="./img/dog.jpg" width="300px" height="300px" class="photo" title="скачать фото"></a><br>
{% else %}
<img alt="фото не загружено" src="./img/nophoto.png" width="300px" height="300px" class="photo" title="фото немає"><br>
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
<details markdown="1"><b>Здійснені заходи з ветеринарного огляду тварини<span title="(ветеринарна допомога, карантинування, дегільментизація, інсектоакарицидна обробка, вакцинація, стерилізація, ідентифікація)" style="color:#d5875c">(?)</span>:</b><br> 
{% if pet.vaccine %}{{ pet.vaccine | newline_to_br }}<br> {% endif %}
<b>Відомості про власника тварини<span title="(ПІБ, місце проживання, договір про передачу тварини у власність)" style="color:#d5875c">(?)</span>:</b> 
{% if pet.owner %}
Хозяин найден! Благодарим за внимание! ({{ pet.owner }})<br> 
{% else %}Что бы забрать питомца к себе, позвоните нам.
<div style="background-color: yellow;">Ищем хозяина! <a href="#/contacts.html"><strong>Контакты</strong></a></div> 
{% endif %}
<b>Природні ознаки:</b> 
{{ pet.signs }}<br> 
<b>Зовнішні ознаки (окрас шерсті, вага, особливі ідентифікуючі ознаки):</b> 
{{ pet.color }}<br> 
<b>Попередня оцінка стану здоров’я тварини:</b> 
{{ pet.health }}<br> 
<b>Відомості про опікуна в разі його наявності (ПІБ, місце проживання):</b> 
{{ pet.guardian }}<br> 
<b>Дата та місце повернення тварини, якщо тварина повернута до ареалу перебування (у місця вилову):</b> 
{{ pet.address }}<br> 
</details> 
<br>
</li>
<br>
{% endfor %}
</ul>
{% comment %}
{% endcomment %}
