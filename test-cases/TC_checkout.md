# Тест-кейсы: Оформление заказа

## TC-027 Checkout — успешный заказ

**Предусловие:** в корзине есть товары
**Шаги:**
1. Нажать "Place Order"
2. Заполнить Name, Country, City, Credit card, Month, Year
3. Нажать "Purchase"

**Expected result:** alert "Thank you for your purchase! ... Id: ...", заказ оформлен
**Priority:** Critical

---

## TC-028 Checkout — пустые обязательные поля

**Шаги:**
1. Открыть форму заказа
2. Оставить все поля пустыми
3. Нажать "Purchase"

**Expected result:** валидация, сообщение об обязательных полях
**Priority:** High
**Actual result:** ⚠️ заказ оформляется с пустыми полями — см. BUG-003

---

## TC-029 Checkout — только Name заполнен

**Шаги:**
1. Заполнить только поле Name
2. Нажать "Purchase"

**Expected result:** валидация остальных полей
**Priority:** High

---

## TC-030 Checkout — некорректный номер карты

**Шаги:**
1. Ввести в Credit card: "abcdef"
2. Заполнить остальные поля корректно
3. Нажать "Purchase"

**Expected result:** ошибка валидации формата карты
**Priority:** Medium
**Actual result:** ⚠️ заказ принимается с любой строкой в поле карты

---

## TC-031 Checkout — Total отображает правильную сумму

**Шаги:**
1. Добавить товары на известную сумму
2. Открыть форму заказа
3. Проверить поле Total

**Expected result:** Total совпадает с суммой товаров в корзине
**Priority:** High

---

## TC-032 Checkout — закрытие формы

**Шаги:**
1. Открыть форму заказа
2. Частично заполнить
3. Нажать "Close"

**Expected result:** форма закрывается, корзина не изменяется
**Priority:** Low
