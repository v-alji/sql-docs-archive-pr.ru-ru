---
title: Соединение с Oracle | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- connOra
ms.assetid: 711ac7ff-5d3d-4533-80ca-d1fecdb3048f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e6546e3bbde666107ed7757c41d98d5b7b598924
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738639"
---
# <a name="connect-to-oracle"></a>Соединение с Oracle
  При первом добавлении или изменении таблиц, используемых на экземпляре CDC, программа может попросить установить соединение с базой данных Oracle. Необходимо ввести учетные данные пользователя Oracle, который имеет доступ к схеме отслеживаемых таблиц. Введите в этом диалоговом окне следующие данные:  
  
 **Аутентификация**  
  
 Выберите один из следующих вариантов:  
  
-   **Проверка подлинности Windows**. Выберите этот параметр, чтобы использовать учетные данные текущего пользователя Windows. Этот параметр можно использовать только в том случае, если в базе данных Oracle настроено использование проверки подлинности Windows.  
  
-   **Проверка подлинности Oracle**. При выборе этого варианта необходимо ввести **Имя пользователя** и **Пароль** пользователя в базе данных Oracle, с которой устанавливается соединение.  
  
## <a name="see-also"></a>См. также:  
 [Добавление таблиц в экземпляр CDC](add-tables-to-a-cdc-instance.md)  
  
  
