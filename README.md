# Тестовое задание по MLSE

Постановка задачи:
- Сделать fork репозитория.
- Реализовать Матлаб-модель [MLSE эквалайзера](https://wirelesspi.com/maximum-likelihood-sequence-estimation-mlse-equalizer/) (оберткой выступает класс mlse.m).
- Модернизировать скрипт для запуска экспериментов (mlseExperiment.m) так, чтобы можно было проанализировать BER от SNR как функцию от номера бита в блоке. Убедиться, что BER не зависит от номера бита в блоке (если это не так, проверьте инициализацию и терминирование Витерби алгоритма).
- Перенести класс mlse.m на С++ и продемонстрировать соответствие Матлаб-модели (способ сравнения С++ реализации и Матлаб-модели на усмотрение кандидата).
- *Предложить* изменения, которые необходимо внести в реализованный эквалайзер, чтобы понизить вычислительную сложность (возможно, путем небольшого уменьшения помехоустойчивости).
- *Кратко* описать результаты в этом README.md, залить весь код в свой fork, сделать merge request.

Требования к оформлению:
- Код С++ должен компилироваться с g++ -std=c++17 (под Линуксом). При необходимости можно написать makefile, однако в таком случае нужно указать, как собирать программу.
- Должно быть использовано осознанное наименование переменных (по смыслу).
- Эквалайзер на С++ должен быть оформлен в виде класса, также должны быть предусмотрены проверки входных данных (защита от дурака).

Реализован ML алгоритм
Для запуска плюсовой версии (отдельно) написан скрипт build.sh (команды для запуска: source build.sh или ./build.sh)
В матлаб версии в функции mlse.m реализован viterbi decoder (на данный момент работает не корректно из-за неправильного взаимодействия с tail data)
Для версии на С++ написана обертка для матлаба (уже встроена в модель, достаточно запустить скрипт как обычно)
 - если не запустится функция make, нужно установить поддерживаемый вашим матлабом компилятор С++ (для mac XCode)