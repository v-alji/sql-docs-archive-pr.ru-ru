---
title: Класс SqlServerAlias | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- SqlServerAlias Class
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SqlServerAlias class
ms.assetid: 475662b9-6985-45bf-b1e9-b0f26ef50443
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 46994409cc6a5119c9144eb7a3a4b9a8a9a22c44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668688"
---
# <a name="sqlserveralias-class"></a><span data-ttu-id="0b69d-102">Класс SqlServerAlias</span><span class="sxs-lookup"><span data-stu-id="0b69d-102">SqlServerAlias Class</span></span>
  <span data-ttu-id="0b69d-103">Класс [SqlServerAlias](sqlserveralias-class.md) представляет псевдоним соединения сервера.</span><span class="sxs-lookup"><span data-stu-id="0b69d-103">The [SqlServerAlias Class](sqlserveralias-class.md) class represents a server connection alias.</span></span>  
  
 <span data-ttu-id="0b69d-104">Псевдоним соединения сервера требуется при возникновении обоих следующих событий:</span><span class="sxs-lookup"><span data-stu-id="0b69d-104">A server connection alias is required when both the following occur:</span></span>  
  
-   <span data-ttu-id="0b69d-105">Клиент подключается к экземпляру [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] по сетевому транспорту, который не является сетевым транспортом по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0b69d-105">The client is connecting to an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] over a network transport that is not the default network transport.</span></span>  
  
-   <span data-ttu-id="0b69d-106">экземпляр [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , с которым соединяется клиент, прослушивает альтернативный именованный канал.</span><span class="sxs-lookup"><span data-stu-id="0b69d-106">The instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to which the client is connected listens on an alternate named pipe.</span></span>  
  
 <span data-ttu-id="0b69d-107">**Примечание.** [Класс SqlServerAlias](sqlserveralias-class.md) наследует `Put` метод от класса поставщика.</span><span class="sxs-lookup"><span data-stu-id="0b69d-107">**Note:** The [SqlServerAlias Class](sqlserveralias-class.md) inherits the `Put` method from the Provider class.</span></span> <span data-ttu-id="0b69d-108">Однако он не возвращает результаты, как указано методом `Provider::Put`.</span><span class="sxs-lookup"><span data-stu-id="0b69d-108">However, it does not return any results as indicated by the `Provider::Put` method.</span></span> <span data-ttu-id="0b69d-109">Дополнительные сведения см. в документации WMI.</span><span class="sxs-lookup"><span data-stu-id="0b69d-109">For more information, see the WMI documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b69d-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="0b69d-110">See Also</span></span>  
 [<span data-ttu-id="0b69d-111">Настройка клиентских протоколов</span><span class="sxs-lookup"><span data-stu-id="0b69d-111">Configure Client Protocols</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
