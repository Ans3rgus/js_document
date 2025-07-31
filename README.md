# js_document
Некоторые интересные моменты из js

Подключение в HTML файле
<script src="alert.js"></script> 

<body>
    <h1>Примеры кода с пояснениями</h1>
    
    <!-- Раздел 1 -->
    <div class="code-section">
        <h2>1. Сортировка пузырьком на JavaScript</h2>
        <pre><code>function bubbleSort(arr) {
    let len = arr.length;
    for (let i = 0; i < len; i++) {
        for (let j = 0; j < len - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                // Меняем элементы местами
                let temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
    return arr;
}

// Пример использования
const numbers = [5, 3, 8, 4, 2];
console.log(bubbleSort(numbers)); // [2, 3, 4, 5, 8]</code></pre>
        
        <div class="explanation">
            <h3>Пояснение:</h3>
            <p>Алгоритм сортировки пузырьком - один из самых простых методов сортировки. Он работает следующим образом:</p>
            <ol>
                <li>Проходим по массиву несколько раз, сравнивая соседние элементы.</li>
                <li>Если текущий элемент больше следующего, меняем их местами.</li>
                <li>После каждого прохода наибольший элемент "всплывает" в конец массива (отсюда название).</li>
                <li>Процесс повторяется для оставшейся части массива.</li>
            </ol>
            <p>Сложность алгоритма: O(n²) в худшем случае.</p>
        </div>
    </div>
    
    <!-- Раздел 2 -->
    <div class="code-section">
        <h2>2. Валидация email с помощью регулярного выражения</h2>
        <pre><code>function isValidEmail(email) {
    const regex = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
    return regex.test(email);
}

// Примеры использования
console.log(isValidEmail("test@example.com")); // true
console.log(isValidEmail("invalid.email@"));    // false</code></pre>
        
        <div class="explanation">
            <h3>Пояснение:</h3>
            <p>Эта функция проверяет, соответствует ли строка формату email адреса с помощью регулярного выражения:</p>
            <ul>
                <li><code>^</code> - начало строки</li>
                <li><code>[a-zA-Z0-9._%+-]+</code> - один или более допустимых символов перед @</li>
                <li><code>@</code> - символ @</li>
                <li><code>[a-zA-Z0-9.-]+</code> - доменное имя (один или более допустимых символов)</li>
                <li><code>\.</code> - точка перед доменом верхнего уровня</li>
                <li><code>[a-zA-Z]{2,}</code> - домен верхнего уровня (2 или более букв)</li>
                <li><code>$</code> - конец строки</li>
            </ul>
            <p>Это базовая валидация, которая не охватывает все возможные случаи, но подходит для большинства стандартных email адресов.</p>
        </div>
    </div>
    
    <!-- Раздел 3 -->
    <div class="code-section">
        <h2>3.
Markup


Анимация плавного появления элемента</h2>
        <pre><code>// CSS
.fade-in {
    opacity: 0;
    transition: opacity 0.5s ease-in;
}

.fade-in.show {
    opacity: 1;
}

// JavaScript
function fadeInElement(element, duration = 500) {
    element.classList.add('fade-in');
    // Запускаем анимацию после добавления класса
    setTimeout(() => {
        element.classList.add('show');
    }, 10);
}

// Пример использования
const box = document.querySelector('.box');
fadeInElement(box);</code></pre>
        
        <div class="explanation">
            <h3>Пояснение:</h3>
            <p>Этот код реализует плавное появление элемента на странице:</p>
            <ol>
                <li>В CSS мы определяем два класса:
                    <ul>
                        <li><code>.fade-in</code> - устанавливает начальную прозрачность 0 и задает анимацию изменения прозрачности</li>
                        <li><code>.show</code> - устанавливает конечную прозрачность 1</li>
                    </ul>
                </li>
                <li>В JavaScript функция <code>fadeInElement</code>:
                    <ul>
                        <li>Добавляет элементу класс <code>fade-in</code></li>
                        <li>Через небольшой таймаут (10ms) добавляет класс <code>show</code>, чтобы запустить анимацию</li>
                        <li>Таймаут нужен, чтобы браузер успел применить начальные стили перед анимацией</li>
                    </ul>
                </li>
            </ol>
            <p>Параметр <code>duration</code> (по умолчанию 500ms) определяет продолжительность анимации.</p>
        </div>
    </div>
</body>
</html>
