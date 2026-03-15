# Тест-кейсы: Регистрация

## TC-009 Registration — успешная регистрация

**Шаги:**
1. Открыть demoblaze.com
2. Нажать "Sign Up"
3. Ввести уникальный username
4. Ввести пароль
5. Нажать "Sign up"

**Expected result:** alert "Sign up successful."
**Priority:** Critical

---

## TC-010 Registration — уже существующий username

**Шаги:**
1. Открыть Sign Up
2. Ввести username, который уже зарегистрирован
3. Ввести пароль
4. Нажать "Sign up"

**Expected result:** alert "This user already exist."
**Priority:** High

---

## TC-011 Registration — пустой username

**Шаги:**
1. Открыть Sign Up
2. Оставить поле username пустым
3. Заполнить пароль
4. Нажать "Sign up"

**Expected result:** валидация поля, alert с просьбой заполнить username
**Priority:** High

---

## TC-012 Registration — пустой пароль

**Шаги:**
1. Открыть Sign Up
2. Заполнить username
3. Оставить поле пароль пустым
4. Нажать "Sign up"

**Expected result:** валидация поля
**Priority:** High
**Actual result:** ⚠️ регистрация проходит успешно с пустым паролем — см. BUG-001

---

## TC-013 Registration — оба поля пустые

**Шаги:**
1. Открыть Sign Up
2. Не заполнять ничего
3. Нажать "Sign up"

**Expected result:** alert "Please fill out Username and Password."
**Priority:** High

---

## TC-014 Registration — пробелы в username

**Шаги:**
1. Ввести username с пробелами в начале/конце ("  user  ")
2. Ввести пароль
3. Нажать "Sign up"

**Expected result:** trimming или ошибка валидации
**Priority:** Medium
// TODO: добавить граничные значения — минимальная длина username

---

## TC-015 Registration — спецсимволы в полях

**Шаги:**
1. Ввести username со спецсимволами: `<script>alert(1)</script>`
2. Нажать "Sign up"

**Expected result:** поле не принимает HTML/JS, либо экранирует символы
**Priority:** Medium

---

## TC-016 Registration — закрытие модалки

**Шаги:**
1. Открыть Sign Up
2. Частично заполнить поля
3. Нажать "Close"
4. Снова открыть Sign Up

**Expected result:** форма очищена
**Priority:** Low

---

## TC-017 Registration — длинный username (граница)

**Шаги:**
1. Ввести username длиной 100+ символов
2. Ввести пароль
3. Нажать "Sign up"

**Ожидаемый результат:** ошибка валидации или ограничение длины поля
**Priority:** Low
