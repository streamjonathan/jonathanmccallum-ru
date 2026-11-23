---
title: "Предложить артиста"
slug: suggest-an-artist
---

Мне очень нравится узнавать музыкантов и артистов, которые следуют за Иисусом. Если ты знаешь кого-то, о ком мне стоит написать, с кем сделать интервью или снять видео-реакцию, — расскажи мне здесь.

Имя и ссылка — этого достаточно. И пара слов о том, почему именно он. Я читаю всё, что приходит. Спасибо большое.

Знаешь кого-то из них? Нажми на фото — форма заполнится сама. Потом добавь пару слов о том, почему именно он, и отправь.

<div class="suggest-carousel" role="list" aria-label="Музыканты и артисты, которых ты можешь предложить">
{% for artist in suggest_carousel %}
  <button type="button" class="suggest-pick" role="listitem" data-artist="{{ artist.name }}" data-link="{{ artist.profile }}" title="Предложить {{ artist.name }}">
    <img src="{{ artist.img }}" alt="{{ artist.name }}" loading="lazy" width="150" height="150">
    <span class="suggest-pick__name">{{ artist.name }}</span>
    <span class="suggest-pick__note">{{ artist.note }}</span>
  </button>
{% endfor %}
</div>

<p class="suggest-carousel__more">Или предложи кого-то нового ниже — любого, о ком мне стоит услышать.</p>

Этот сайт не для тех, кому нет 18 лет.

<form id="suggest-form" class="suggest-form">
  <label for="suggest-artist">Имя артиста</label>
  <input id="suggest-artist" name="artist" type="text" maxlength="200" placeholder="На кого мне посмотреть?" required>

  <label for="suggest-link">Ссылка на профиль в соцсетях</label>
  <input id="suggest-link" name="link" type="url" maxlength="500" placeholder="https://www.instagram.com/…" required>

  <fieldset class="suggest-kinds">
    <legend>Что мне с ним сделать?</legend>
    <label><input type="checkbox" name="kind" value="write"> Написать о нём</label>
    <label><input type="checkbox" name="kind" value="interview"> Сделать интервью</label>
    <label><input type="checkbox" name="kind" value="reaction"> Снять видео-реакцию</label>
  </fieldset>

  <label for="suggest-why">Почему именно он?</label>
  <textarea id="suggest-why" name="why" rows="3" maxlength="500" placeholder="Пары слов хватит…"></textarea>

  <label for="suggest-name">Твоё имя <span class="optional">(необязательно)</span></label>
  <input id="suggest-name" name="fromName" type="text" maxlength="100" placeholder="Чтобы я мог поблагодарить тебя">

  <label for="suggest-from-link">Ссылка на твой профиль в соцсетях <span class="optional">(необязательно)</span></label>
  <input id="suggest-from-link" name="fromLink" type="url" maxlength="500" placeholder="https://www.instagram.com/…">

  <button id="suggest-button" type="button">Отправить предложение</button>

  <p id="suggest-result" aria-live="polite"></p>
</form>
