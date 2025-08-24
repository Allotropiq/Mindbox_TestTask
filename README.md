## Mindbox_TestTask
### Тестовое задание на позицию стажер DevOps в команию MindBox

#### Задание требует создать yaml-манифест для kubernetes, который будет учитывать следующие вводные:
* Кластер состоящий из 5 нод находящийся в трех разных зонах.
* Приложение требует около 5-10 секунд для инициализации.
* 4 пода справляются с пиковой нагрузкой (результат нагрузочного теста).
* На первые запросы приложению требуется значительно больше ресурсов CPU, в дальнейшем потребление ровное в районе 0.1 CPU. По памяти всегда “ровно” в районе 128M memory
* Приложение имеет дневной цикл по нагрузке.
* Максимальная отказоустойчивость.
* Минимальное потребеление ресурсов.

#### Учитывая вышеперечисленные факторы мною было разработано решение:

### [***Кофигурация развертывания подов в kubernetes кластерe***](deployment.yaml)

**Источники, которые способстовали принятию и поиску решений:**
* [Официальный сайт с документацией kubernetes](https://kubernetes.io/ru/docs/home/)
    * [Настройка Liveness, Readiness и Startup проб](https://kubernetes.io/ru/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/)
    * [Распределение подов по узлам](https://kubernetes.io/ru/docs/concepts/scheduling-eviction/assign-pod-node/)
    * [Метки и селекторы](https://kubernetes.io/ru/docs/concepts/overview/working-with-objects/labels/)
    * [Выполнение плавающего обновления](https://kubernetes.io/ru/docs/tutorials/kubernetes-basics/update/update-intro/)
* [Сайт Habr](https://habr.com/ru/feed/)
    * [Автоскейлинг микросервисов с HPA в Kubernetes](https://habr.com/ru/companies/otus/articles/838364/)
    * [Kubernetes: почему так важно настроить управление ресурсами системы?](https://habr.com/ru/companies/nixys/articles/480072/)
    * [Использование affinity-правил Kubernetes для контроля назначения подов](https://habr.com/ru/companies/otus/articles/576944/)
* [Плейлист "kubernetes"от ютуб канала ADV-IT](https://www.youtube.com/playlist?list=PLg5SS_4L6LYvN1RqaVesof8KAf-02fJSi)
* [Обучающий материал от timewev.cloud](https://timeweb.cloud/tutorials/)
    * [Что такое Kubernetes Deployment и как его использовать](https://timeweb.cloud/tutorials/kubernetes/kubernetes-deployment-chto-eto-i-kak-rabotaet)
    * [Liveness, Readiness и Startup Probes в Kubernetes](https://timeweb.cloud/tutorials/kubernetes/liveness-readiness-startup-probes-v-kubernetes)
* А также бесплатные LLM для более подробного объяснения более мелких деталей.
