function calculateScore() {
    const form = document.getElementById('quiz-form');
    let score = 0;

    // Soma os pontos das respostas
    for (let i = 1; i <= 10; i++) {
        const question = form['q' + i];
        if (question) {
            const answer = [...question].find(input => input.checked);
            if (answer) {
                score += parseInt(answer.value);
            }
        }
    }

    // Exibe o resultado
    const result = document.getElementById('result');
    if (score <= 15) {
        result.textContent = 'Uso saudável - Você parece ter controle sobre seu uso das redes sociais.';
    } else if (score <= 25) {
        result.textContent = 'Uso moderado - Você utiliza as redes, mas deve ficar atento ao tempo gasto.';
    } else if (score <= 35) {
        result.textContent = 'Uso elevado - Indícios de dependência, seria interessante refletir sobre o impacto na sua rotina.';
    } else {
        result.textContent = 'Uso problemático - Sinais fortes de dependência, considere buscar maneiras de reduzir o tempo online.';
    }
}
