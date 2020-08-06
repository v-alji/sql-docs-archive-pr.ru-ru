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
# <a name="connect-to-oracle"></a><span data-ttu-id="9b664-102">Соединение с Oracle</span><span class="sxs-lookup"><span data-stu-id="9b664-102">Connect to Oracle</span></span>
  <span data-ttu-id="9b664-103">При первом добавлении или изменении таблиц, используемых на экземпляре CDC, программа может попросить установить соединение с базой данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="9b664-103">When you add or edit the tables used in the CDC instance for the first time, you may be asked to connect to the Oracle database.</span></span> <span data-ttu-id="9b664-104">Необходимо ввести учетные данные пользователя Oracle, который имеет доступ к схеме отслеживаемых таблиц.</span><span class="sxs-lookup"><span data-stu-id="9b664-104">You should enter the credentials of an Oracle user who can access the schema of the tables to be captured.</span></span> <span data-ttu-id="9b664-105">Введите в этом диалоговом окне следующие данные:</span><span class="sxs-lookup"><span data-stu-id="9b664-105">Enter the following in this dialog box:</span></span>  
  
 <span data-ttu-id="9b664-106">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="9b664-106">**Authentication**</span></span>  
  
 <span data-ttu-id="9b664-107">Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="9b664-107">Select one of the following:</span></span>  
  
-   <span data-ttu-id="9b664-108">**Проверка подлинности Windows**. Выберите этот параметр, чтобы использовать учетные данные текущего пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="9b664-108">**Windows Authentication**: Select this to use the current Windows domain credentials.</span></span> <span data-ttu-id="9b664-109">Этот параметр можно использовать только в том случае, если в базе данных Oracle настроено использование проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="9b664-109">You can use this option only if the Oracle database is configured to work with Windows authentication.</span></span>  
  
-   <span data-ttu-id="9b664-110">**Проверка подлинности Oracle**. При выборе этого варианта необходимо ввести **Имя пользователя** и **Пароль** пользователя в базе данных Oracle, с которой устанавливается соединение.</span><span class="sxs-lookup"><span data-stu-id="9b664-110">**Oracle Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the Oracle database you are connecting to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b664-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="9b664-111">See Also</span></span>  
 [<span data-ttu-id="9b664-112">Добавление таблиц в экземпляр CDC</span><span class="sxs-lookup"><span data-stu-id="9b664-112">Add Tables to a CDC Instance</span></span>](add-tables-to-a-cdc-instance.md)  
  
  
