let vokabeln = [];

function addVokabel() {
    const vokabel = document.getElementById('vokabel').value;
    const bedeutung = document.getElementById('bedeutung').value;

    if (vokabel && bedeutung) {
        vokabeln.push({ vokabel, bedeutung });
        displayVokabeln();
        document.getElementById('vokabel').value = '';
        document.getElementById('bedeutung').value = '';
    } else {
        alert('Bitte geben Sie sowohl die Vokabel als auch die Bedeutung ein.');
    }
}

function displayVokabeln() {
    const vokabelnList = document.getElementById('vokabeln');
    vokabelnList.innerHTML = '';
    vokabeln.forEach((item, index) => {
        vokabelnList.innerHTML += `
            <li>
                ${item.vokabel} - ${item.bedeutung} 
                <button onclick="deleteVokabel(${index})">Löschen</button>
            </li>
        `;
    });
}

function deleteVokabel(index) {
    vokabeln.splice(index, 1);
    displayVokabeln();
}

function startQuiz() {
    if (vokabeln.length === 0) {
        alert('Keine Vokabeln zum Abfragen verfügbar.');
        return;
    }

    const quizDiv = document.getElementById('quiz');
    quizDiv.innerHTML = '';

    const randomIndex = Math.floor(Math.random() * vokabeln.length);
    const selectedVokabel = vokabeln[randomIndex];

    quizDiv.innerHTML = `
        <p>Was bedeutet "${selectedVokabel.vokabel}"?</p>
        <input type="text" id="quizAnswer" placeholder="Antwort eingeben">
        <button onclick="checkAnswer('${selectedVokabel.bedeutung}')">Überprüfen</button>
    `;
}

function checkAnswer(correctAnswer) {
    const userAnswer = document.getElementById('quizAnswer').value;
    if (userAnswer.toLowerCase() === correctAnswer.toLowerCase()) {
        alert('Richtig!');
    } else {
        alert('Falsch! Die richtige Antwort ist: ' + correctAnswer);
    }
    startQuiz();
}
