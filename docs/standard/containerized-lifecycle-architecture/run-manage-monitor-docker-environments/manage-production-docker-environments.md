---
title: Управление Docker рабочих сред
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 169ffa7ba61fa5dff09229410adb534f8e34a35c
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37104589"
---
# <a name="manage-production-docker-environments"></a>Управление Docker рабочих сред

Управление кластером и orchestration — это процесс управления группой узлов. Это может включать добавление и удаление узлов из кластера, получение сведений о текущем состоянии узлов и контейнеров и запуск и остановка процессов. Кластер управления и оркестрации тесно связана с планированием, поскольку планировщик должен иметь доступ к каждому узлу в кластере для планирования служб. По этой причине часто используется то же самое средство для обоих назначений.

## <a name="container-service-and-management-tools"></a>Контейнер службы и средства управления

Контейнер службы обеспечивает быстрое развертывание решений кластеризации и orchestration популярных контейнер с открытым исходным кодом. Чтобы обеспечить полную переносимость контейнеры вашего приложения в нем образов Docker. С помощью службы контейнеров, можно развернуть КД/OS (на платформе Mesosphere и Apache Mesos) и помощью Docker Swarm кластеры с шаблонов диспетчера ресурсов Azure или портал Azure, чтобы убедиться, что можно масштабировать до тысяч эти приложения — даже десятков тысяч — из контейнеры.

Развернуть эти кластеры с помощью набора масштабирования виртуальной машины Azure и кластеры воспользоваться преимуществами предложениями сети и хранилища Azure. Для доступа к службе контейнера, необходимо получить подписку Azure. Со службой контейнера можно воспользоваться преимуществами высококлассные возможности Azure одновременно сохраняя переносимость приложения, включая на уровнях orchestration.

Таблица 6-1 перечислены стандартные инструменты управления, связанных с их orchestrators, планировщиков и кластеризации платформы.

Средства управления Docker таблица 6-1.


| Средства управления      | Описание:           | Связанные orchestrators |
|-----------------------|-----------------------|-----------------------|
| Контейнер службы\(управления пользовательского интерфейса на портале Azure) | [Контейнер службы](https://azure.microsoft.com/en-us/services/container-service/) предоставляет удобно получать способ работы [развернуть кластер контейнера в Azure](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment) основании популярных orchestrators как Mesosphere DC/OS, Kubernetes и помощью Docker Swarm. <br /><br /> Контейнер службы оптимизирует конфигурацию этих платформ. Необходимо выбрать размер, количество узлов, а также инструменты orchestrator и контейнер службы обрабатывает все остальное. | Mesosphere DC/OS <br /><br /> Kubernetes <br /><br /> Docker Swarm |
| Docker универсальной плоскости управления\(локально или в облаке) | [Docker универсальной плоскости управления](https://docs.docker.com/v1.11/ucp/overview/) — решение управления кластера корпоративного уровня с Docker. Он позволяет управлять весь кластер из одного места. <br /><br /> Docker универсальной плоскости управления включен в состав коммерческого продукт с именем Docker центра обработки данных, который предоставляет помощью Docker Swarm, универсальной плоскости управления Docker и доверенный реестр Docker. <br /><br /> Docker центра обработки данных может быть установленный в локальной или подготовить из общедоступного облака, таких как Azure. | Помощью docker Swarm\(поддерживается службой контейнера) |
| Облако docker\(также называется Tutum; облака SaaS) | [Облако docker](https://docs.docker.com/docker-cloud/) — это служба управления размещенного (SaaS), которая предоставляет возможности orchestration и реестр Docker построения и тестирования возможности изображения Dockerized приложений, средства, которые помогут создать и настроить инфраструктуру хост-компьютера, и функций развертывания для автоматизации развертывания изображения к конкретной инфраструктуре. Учетной записи облачного Docker SaaS можно подключиться к инфраструктуре в контейнер службы, работу кластера с помощью Docker Swarm. | Помощью docker Swarm\(поддерживается службой контейнера) |
| Mesosphere Marathon\(локально или в облаке) | [Marathon](https://mesosphere.github.io/marathon/docs/marathon-ui.html) — платформа orchestration и планировщик контейнера производственного класса для контроллера домена/OS и Apache Mesos Mesosphere элемента. <br /><br /> Она работает с Mesos (контроллера домена или ОС на основе Apache Mesos) для управления длительной службы и предоставляет [веб-Интерфейсе для процесса и управления контейнером](https://mesosphere.github.io/marathon/docs/marathon-ui.html). Он предоставляет веб-инструмент управления пользовательского интерфейса | Mesosphere DC/OS\(основании Apache Mesos; поддерживается службой контейнера) |
| Google Kubernetes | [Kubernetes](http://kubernetes.io/docs/user-guide/ui/#dashboard-access) охватывает управляя операциями, планирования и инфраструктуру кластера. Это открытая платформа для автоматического развертывания, масштабирование и операций контейнеров приложения ко всем кластерам узлов, предоставляя ориентированное контейнера инфраструктуры. | Google Kubernetes\(поддерживается службой контейнера) |

## <a name="azure-service-fabric"></a>Azure Service Fabric

Другой вариант для развертывания кластера и управления является Azure Service Fabric. [Service Fabric](https://azure.microsoft.com/en-us/services/service-fabric/) модели для создания высокомасштабируемых микрослужбами приложений программирования Microsoft микрослужбами платформу, которая включает orchestration контейнера, а также разработчика. Service Fabric поддерживает Docker в текущей версии Linux предварительного просмотра, как и в [preview Service Fabric в Linux](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere)и для контейнеров Windows [в следующем выпуске](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Ниже приведены средства управления структурой службы:

-   [Портал Azure для Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal) операций, связанных с кластера (Создание, обновление или удаление) кластере или настроить свою инфраструктуру (виртуальных машин, подсистемы балансировки нагрузки, сети и т. д.)

-   [Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) — средство пользовательского интерфейса в Интернете, которое предоставляет аналитики и кластер Service Fabric с точки зрения узлы или виртуальные машины, а также из приложения и службы точки зрения определенных операций.


>[!div class="step-by-step"]
[Назад](run-microservices-based-applications-in-production.md)
[Вперед](monitor-containerized-application-services.md)
