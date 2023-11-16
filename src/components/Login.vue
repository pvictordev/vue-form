<template>
  <div>
    <form action="#" id="personalInfoForm" @submit.prevent="submitForm">
      <fieldset>
        <legend>Атрибуты формы</legend>
        <div>
          <label for="surname">Введите вашу Фамилию:</label>
          <input
            type="text"
            id="surname"
            name="surname"
            placeholder="Введите вашу Фамилию"
            required
          /><br /><br />

          <label for="firstName">Введите ваше Имя:</label>
          <input
            type="text"
            id="firstName"
            name="firstName"
            placeholder="Введите ваше Имя"
            required
          /><br /><br />

          <label for="patronymic">Введите ваше Отчество:</label>
          <input
            type="text"
            id="patronymic"
            name="patronymic"
            placeholder="Введите ваше Отчество"
            required
          /><br /><br />

          <label for="birthDate">Введите дату вашего Рождения:</label>
          <input type="date" id="birthDate" name="birthDate" required /><br /><br />

          <label for="phoneNumber">Введите ваш номер телефона:</label>
          <input
            type="tel"
            id="phoneNumber"
            name="phoneNumber"
            maxlength="11"
            value="+7"
            required
          /><br /><br />

          <div>
            <label>Выберите ваш пол:</label><br />
            <label for="male">Мужской</label>
            <input type="radio" id="male" name="sex" value="male" />
            <label for="female">Женский</label>
            <input type="radio" id="female" name="sex" value="female" />
          </div>

          <label for="clients">Группа клиентов:</label>
          <select name="clients" id="clients" required>
            <option value="vip">VIP</option>
            <option value="problematic">Проблемные</option>
            <option value="oms">ОМС</option>
          </select>

          <label for="doctor">Лечащий врач:</label>
          <select name="doctor" id="doctor">
            <option value="ivanov">Иванов</option>
            <option value="zakharov">Захаров</option>
            <option value="chernysheva">Чернышева</option>
          </select>

          <label for="noSMS">Не отправлять СМС:</label>
          <input type="checkbox" id="noSMS" name="noSMS" /><br /><br />
        </div>
      </fieldset>

      <fieldset>
        <legend>Адрес</legend>
        <label for="index">Индекс:</label>
        <input type="text" id="index" name="index" /><br /><br />

        <label for="country">Страна:</label>
        <input type="text" id="country" name="country" /><br /><br />

        <label for="region">Область:</label>
        <input type="text" id="region" name="region" /><br /><br />

        <label for="city">Город:</label>
        <input type="text" id="city" name="city" required /><br /><br />

        <label for="street">Улица:</label>
        <input type="text" id="street" name="street" /><br /><br />

        <label for="house">Дом:</label>
        <input type="text" id="house" name="house" /><br /><br />
      </fieldset>

      <fieldset>
        <legend>Паспорт</legend>
        <label for="docType">Тип документа:</label>
        <select id="docType" name="docType" required>
          <option value="passport">Паспорт</option>
          <option value="birthCertificate">Свидетельство о рождении</option>
          <option value="driverLicense">Вод. удостоверение</option></select
        ><br /><br />

        <label for="series">Серия:</label>
        <input type="text" id="series" name="series" /><br /><br />

        <label for="number">Номер:</label>
        <input type="text" id="number" name="number" /><br /><br />

        <label for="issuedBy">Кем выдан:</label>
        <input type="text" id="issuedBy" name="issuedBy" /><br /><br />

        <label for="issueDate">Дата выдачи:</label>
        <input type="date" id="issueDate" name="issueDate" required /><br /><br />
      </fieldset>

      <input type="submit" value="Отправить" />
    </form>
  </div>
</template>

<script>
export default {
  name: 'Login',
  methods: {
    submitForm() {
      // Получаем все обязательные поля
      const requiredFields = document.querySelectorAll('[required]')

      // Проверяем, все ли обязательные поля заполнены
      let allFieldsFilled = true
      requiredFields.forEach((field) => {
        if (!field.value.trim()) {
          allFieldsFilled = false
        }
      })

      // Если все поля заполнены, выводим сообщение
      if (allFieldsFilled) {
        alert('Клиент успешно создан')
      } else {
        // Если есть незаполненные поля, вы можете выполнить другие действия или вывести сообщение об ошибке
        alert('Пожалуйста, заполните все обязательные поля')
      }
    }
  }
}
</script>

<style src="../assets/login.css"></style>
