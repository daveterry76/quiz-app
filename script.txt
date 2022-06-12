'use strict';

let score = 0;

const firstNextBtn = document.getElementById('first-next-btn');
const secondNextBtn = document.getElementById('second-next-btn');
const finishBtn = document.getElementById('finish-btn');
const retryBtn = document.querySelector('.retry-btn');

const displaySecondCard = function () {
    document.querySelector('.first-card').classList.add('hidden');
    document.querySelector('.second-card').classList.remove('hidden');
}

const displayThirdCard = function () {
    document.querySelector('.second-card').classList.add('hidden');
    document.querySelector('.third-card').classList.remove('hidden');
}

const hideThirdCard = function () {
    document.querySelector('.third-card').classList.add('hidden');
}



firstNextBtn.addEventListener('click', function () {
    displaySecondCard();

    if (document.getElementById('javascript').checked) {
        score += 1;
    } else if (document.getElementById('ruby').checked || document.getElementById('flutter').checked) {
        score += 0;
    }

});

secondNextBtn.addEventListener('click', function () {
    displayThirdCard();

    if (document.getElementById('year-three').checked) {
        score += 1;
    } else if (document.getElementById('year-two').checked || document.getElementById('year-one').checked) {
        score += 0;
    }
});

finishBtn.addEventListener('click', function () {
    hideThirdCard();

    if (document.getElementById('pc').checked) {
        score += 1;
    } else if (document.getElementById('phone').checked || document.getElementById('mac').checked) {
        score += 0;
    }

    if (score === 0) {
        document.querySelector('.zero-score').textContent = score;
        document.querySelector('.zero-card').classList.remove('hidden');

    } else if (score === 1) {
        document.querySelector('.one-score').textContent = score;
        document.querySelector('.one-card').classList.remove('hidden');

    } else if (score === 2) {
        document.querySelector('.two-score').textContent = score;
        document.querySelector('.two-card').classList.remove('hidden');

    } else if (score === 3) {
        document.querySelector('.three-score').textContent = score;
        document.querySelector('.three-card').classList.remove('hidden');

    }

});


retryBtn.addEventListener('click', function () {
    score = 0;
    document.querySelector('.first-card').classList.remove('hidden');
})