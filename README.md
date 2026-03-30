
# Лабораторная работа №20. Работа с DOM и событиями в JavaScript
## Основная информация

**ФИО:** Текутова Виктория Денисовна

**Группа:** ИСП-231

**Дата:** 30.03.2026

## Краткое описание работы
В ходе выполнения лабораторной работы были изучены основные принципы работы с DOM (Document Object Model) и событиями в JavaScript. Были освоены следующие навыки:
- Поиск HTML-элементов с помощью методов `getElementById()` и `querySelector()`
- Изменение содержимого и стилей элементов через JavaScript
- Обработка событий пользователя (клики, ввод текста, отправка форм)
- Создание динамических элементов
- Валидация данных форм
- Делегирование событий для динамически созданных элементов

## Структура проекта
- index.html
- main.js
- style.css
- dynamicElements.html
- dynamicElements.js
- img/
- README.md

## Сравнение с C# (WinForms/WPF)

### DOM в JS = Controls в C# WinForms

| Концепция | C# (WinForms) | JavaScript (DOM) |
|-----|-----|-----|
| Найти элемент | `Button myButton = this.Controls["myButton"]` | `const myButton = document.getElementById("myButton")` |
| Изменить текст | `label1.Text = "Новый текст"` | `label1.textContent = "Новый текст"` |
| Добавить обработчик | `button1.Click += HandleClick` | `button.addEventListener("click", handleClick)` |
| Создать элемент | `Button btn = new Button()` | `const btn = document.createElement("button")` |
| Добавить в контейнер | `panel1.Controls.Add(btn)` | `panel.appendChild(btn)` |
| Скрыть элемент | `button1.Visible = false` | `button.style.display = "none"` |

### Events в JS = События в C#

**C# (WinForms):**
```csharp
private void Button1_Click(object sender, EventArgs e) {
    label1.Text = "Нажато!";
}
```
**JavaScript (DOM):**
```javascript
button.addEventListener("click", (e) => {
    label.textContent = "Нажато!";
});
```
### Валидация формы
**C# (WinForms):**
```csharp
private void SubmitButton_Click(object sender, EventArgs e) {
    if (string.IsNullOrEmpty(nameTextBox.Text)) {
        MessageBox.Show("Введите имя!");
        return;
    }
    // ...
}
```
**JavaScript (DOM):**
```javascript
form.addEventListener("submit", (e) => {
    e.preventDefault();
    if (!nameInput.value.trim()) {
        alert("Введите имя!");
        return;
    }
    // ...
});
```

### Главные отличия

| Аспект | C# WinForms | JavaScript DOM |
|--------|-------------|----------------|
| Компиляция | Да | Нет (интерпретация) |
| Типизация | Строгая | Динамическая |
| Ошибки | Во время компиляции | Во время выполнения |
| UI-дизайнер | Есть (визуальный) | Нет (только код) |
| Платформа | Windows | Любой браузер |

### Преимущества DOM перед WinForms

- Кроссплатформенность (работает везде)
- Не нужна установка приложения
- Легко обновлять (обновил файлы — всё работает)
- Современные UI (CSS, анимации)

### Преимущества WinForms перед DOM

- Визуальный дизайнер (drag & drop)
- Ошибки на этапе компиляции
- Интеграция с Windows API
- Более понятная структура

### Вывод
DOM и WinForms решают схожие задачи, но разными подходами.
