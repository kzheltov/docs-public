Перед обновлением рекомендуем сохранить важные данные и приложения, произвести резервное копирование, а также произвести операцию обновления на копиях кластера для предотвращения возможных проблем и потери данных.

<warn>

- Обновить версию кластера можно только на более новую. Обратная операция или понижение версии невозможно.
- При обновлении версии кластера до версии Kubernetes 1.23 и выше с [неотключаемой технологией SSO](../../k8s-concepts/k8s-sso), в обновленном кластере также будет принудительно включена SSO.

</warn>

Обновление кластера версии 1.16 и ниже возможно осуществить только через операцию создания нового кластера. Для выполнения подобной операции рекомендуется [воспользоваться программным обеспечением Velero](/ru/base/k8s/k8s-addons/k8s-backups) для резервного копирования кластера с последующим восстановлением в более новую версию.

Обновление в Панели VK Cloud
-----------------------

Обновления версии кластера производится в разделе «Контейнеры» Панели VK Cloud. Для этого следует выбрать в контекстном меню необходимого кластера соответствующую опцию «Обновить версию»:

Во всплывающем окне нужно выбрать желаемую новую версию и подтвердить смену версии кнопкой «Изменить версию».

Во время выполнения операции обновления, ноды кластера будет перезагружены. Сначала будут обновлены master-узлы, потом node узлы.

<info>

Вы можете управлять количеством одновременно перезагруженных нод через меню «Настройки обновления нод». Подробнее о процессе настройки вы можете узнать в статье [«Настройки обновления нод»](../../k8s-node-groups/config-update-node/config-update-node.md).

</info>

В случае обновления кластера с 1 master-узлом или 1 node-узлом возможны перебои в работе вашего приложения, т.к. все его реплики будут находиться на узле, который обновляется.

В случае обновления кластера с 3 master-узлами и 2 и более node-узлами, обновление будет произведено с минимальным влиянием (или без такового) на работоспособность конечных приложений. Это будет зависеть от архитектуры приложений, доступных ресурсов на узлах и существующих подов.
