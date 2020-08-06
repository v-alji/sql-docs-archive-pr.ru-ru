---
title: Шаг 3. Добавление и настройка диспетчера соединений OLE DB | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e7b74cba-a0e5-4478-af12-3f81b9484e9e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3bc4c885ce6c39c72031dd3b528a769cd47ac8f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664361"
---
# <a name="step-3-adding-and-configuring-an-ole-db-connection-manager"></a>Шаг 3. Добавление и настройка диспетчера соединений OLE DB
  После добавления диспетчера соединений с неструктурированными файлами для подключения к источникам данных предстоит добавить диспетчер соединений OLE DB для соединения с назначением. Диспетчер соединений OLE DB позволяет пакету получать данные из любого источника данных, совместимого с OLE DB, а также загружать данные в такой источник данных. Используя диспетчер соединений OLE DB, можно указать для соединения сервер, метод проверки подлинности и базу данных по умолчанию.  
  
 На этом занятии будет создан диспетчер соединений OLE DB, использующий проверку подлинности Windows для подключения к локальному экземпляру **AdventureWorksDB2012**. На создаваемый диспетчер соединений OLE DB также будут ссылаться другие компоненты, которые будут созданы позже в ходе работы с этим учебником, такие, как преобразование «Уточняющий запрос» и назначение OLE DB.  
  
### <a name="to-add-and-configure-an-ole-db-connection-manager-to-the-ssis-package"></a>Добавление и настройка диспетчера соединений OLE DB для пакета служб SSIS  
  
1.  Щелкните правой кнопкой мыши область **Диспетчеры соединений** и выберите команду **Создать соединение OLE DB**.  
  
2.  В диалоговом окне **Настройка диспетчера соединений OLE DB** нажмите кнопку **Создать**.  
  
3.  Введите **localhost**в поле **Имя сервера**.  
  
     Если в качестве имени сервера указано значение localhost, диспетчер соединений соединяется с экземпляром [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , расположенном по умолчанию на локальном компьютере. Чтобы использовать удаленный экземпляр [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], замените localhost именем сервера, с которым нужно соединиться.  
  
4.  Убедитесь, что в группе **Вход на сервер** выбран вариант **Использовать проверку подлинности Windows** .  
  
5.  В группе **соединение с базой данных** в поле **выберите или введите имя базы данных** введите или выберите `AdventureWorksDW2012` .  
  
6.  Нажмите кнопку **Проверить соединение** , чтобы убедиться, что параметры соединения указаны правильно.  
  
7.  Нажмите кнопку **ОК**.  
  
8.  Нажмите кнопку **ОК**.  
  
9. Убедитесь, что на панели **Подключение к данным** в диалоговом окне **Настройка диспетчера соединений OLE DB** выбрано значение **localhost.AdventureWorksDW2012** .  
  
10. Нажмите кнопку **ОК**.  
  
## <a name="next-task-in-lesson"></a>Следующая задача занятия  
 [Этап 4. Добавление задачи потока данных в пакет](lesson-1-4-adding-a-data-flow-task-to-the-package.md)  
  
## <a name="see-also"></a>См. также:  
 [Диспетчер соединений OLE DB](connection-manager/ole-db-connection-manager.md)  
  
  