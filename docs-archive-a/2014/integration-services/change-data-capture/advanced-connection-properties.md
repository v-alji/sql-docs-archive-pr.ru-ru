---
title: Дополнительные свойства соединения | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4edfab68-7e68-45e8-a3f3-a0049ff7eb9e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8dc844d1fdfb1e82f0ffa8de93a6a1060ef190cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666202"
---
# <a name="advanced-connection-properties"></a><span data-ttu-id="4cdac-102">Дополнительные свойства соединения</span><span class="sxs-lookup"><span data-stu-id="4cdac-102">Advanced Connection Properties</span></span>
  <span data-ttu-id="4cdac-103">В диалоговом окне **Дополнительные свойства соединения** можно добавить дополнительные параметры в строку подключения.</span><span class="sxs-lookup"><span data-stu-id="4cdac-103">Use the **Advanced Connection Properties** dialog box to add more connection parameters to the connection string.</span></span>  
  
 <span data-ttu-id="4cdac-104">В качестве дополнительных можно использовать любые параметры соединения ODBC, поддерживаемые используемым экземпляром базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4cdac-104">The additional connection parameters can be any ODBC connection parameter that is supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database instance you are using.</span></span>  
  
 <span data-ttu-id="4cdac-105">Параметры, указанные в диалоговом окне **Дополнительные свойства соединения** , добавляются к параметрам, выбранным в диалоговом окне **Соединение с SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="4cdac-105">The parameters added using the **Advanced Connection Properties** dialog box are added to the parameters selected in the **Connect to SQL Server** dialog box.</span></span>  
  
 <span data-ttu-id="4cdac-106">Последний экземпляр каждого заданного параметра переопределяет все предыдущие экземпляры этого параметра.</span><span class="sxs-lookup"><span data-stu-id="4cdac-106">The last instance of each parameter provided overrides any previous instances of the parameter.</span></span> <span data-ttu-id="4cdac-107">Параметры, добавленные в диалоговом окне **Дополнительные параметры соединения** , дополняют и заменяют параметры, заданные в диалоговом окне **Соединение с SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="4cdac-107">Parameters added using the **Advanced Connection Parameters** dialog box follow and replace the parameters provided in the **SQL Server Connection** dialog box.</span></span> <span data-ttu-id="4cdac-108">Например, если в диалоговом окне **Соединение с SQL Server** в качестве имени сервера указано SERVER1, а диалоговое окно **Дополнительные параметры соединения** содержит строку ;SERVER=SERVER2, то соединение будет установлено с сервером SERVER2.</span><span class="sxs-lookup"><span data-stu-id="4cdac-108">For example, if the **SQL Server Connection** dialog box specifies SERVER1 as the Server name, and the **Additional Connection Parameters** page contains ;SERVER=SERVER2, the connection will be made to SERVER2.</span></span>  
  
 <span data-ttu-id="4cdac-109">Параметры, добавляемые в диалоговом окне **Дополнительные свойства соединения** , передаются в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="4cdac-109">Parameters added using the **Advanced Connection Properties** dialog box are passed as plain text.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4cdac-110">Не указывайте учетные данные для входа в диалоговом окне **Дополнительные свойства соединения** .</span><span class="sxs-lookup"><span data-stu-id="4cdac-110">Do not include login credentials in the **Advanced Connection Properties** dialog box.</span></span> <span data-ttu-id="4cdac-111">Они не будут зашифрованы при передаче по сети.</span><span class="sxs-lookup"><span data-stu-id="4cdac-111">They will not be encrypted when they are passed across the network.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cdac-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="4cdac-112">See Also</span></span>  
 <span data-ttu-id="4cdac-113">[Доступ к консоли конструктора CDC](access-the-cdc-designer-console.md) </span><span class="sxs-lookup"><span data-stu-id="4cdac-113">[Access the CDC Designer Console](access-the-cdc-designer-console.md) </span></span>  
 [<span data-ttu-id="4cdac-114">Соединение с SQL Server для создания экземпляров</span><span class="sxs-lookup"><span data-stu-id="4cdac-114">SQL Server Connection for Instance Creation</span></span>](sql-server-connection-for-instance-creation.md)  
  
  
