---
title: Подключение к служебной программе SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: b9b90b8d-241f-4b74-ac14-de7b10ea1821
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e8e59a28e083fc302faebbcba932c18a04e73a7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656400"
---
# <a name="connect-to-a-sql-server-utility"></a><span data-ttu-id="77a54-102">Подключение к служебной программе SQL Server</span><span class="sxs-lookup"><span data-stu-id="77a54-102">Connect to a SQL Server Utility</span></span>
  <span data-ttu-id="77a54-103">Перед подключением к программе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] необходимо создать точку управления служебной программой.</span><span class="sxs-lookup"><span data-stu-id="77a54-103">Before you can connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, you must create a utility control point (UCP).</span></span> <span data-ttu-id="77a54-104">Дополнительные сведения см. в разделе [Функции и задачи служебной программы SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="77a54-104">For more information, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>

 <span data-ttu-id="77a54-105">Для просмотра работоспособности ресурсов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и управления ей подключитесь к программе [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] с помощью среды [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SSMS).</span><span class="sxs-lookup"><span data-stu-id="77a54-105">To view and manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resource health, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (SSMS) to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>

 <span data-ttu-id="77a54-106">Подключение к программе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью среды SSMS.</span><span class="sxs-lookup"><span data-stu-id="77a54-106">To connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility through SSMS:</span></span>

1.  <span data-ttu-id="77a54-107">Запустите среду SSMS.</span><span class="sxs-lookup"><span data-stu-id="77a54-107">Launch SSMS.</span></span>

2.  <span data-ttu-id="77a54-108">В среде SSMS подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77a54-108">In SSMS, connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>

3.  <span data-ttu-id="77a54-109">В меню **Вид** выберите пункт **Обозреватель служебных программ**.</span><span class="sxs-lookup"><span data-stu-id="77a54-109">Click **View** and then **Utility Explorer**.</span></span>

4.  <span data-ttu-id="77a54-110">На панели навигации обозревателя служебных программы щелкните ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Соединение со служебной программой**.</span><span class="sxs-lookup"><span data-stu-id="77a54-110">In the Utility Explorer navigation pane, click ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Connect to Utility**.</span></span>

5.  <span data-ttu-id="77a54-111">В диалоговом окне **Подключение к серверу** укажите имя экземпляра точки управления служебной программой (UCP) и нажмите кнопку **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="77a54-111">In the **Connect to Server** dialog box, specify the UCP instance name, then click **Connect**.</span></span>

6.  <span data-ttu-id="77a54-112">Откройте панель навигации обозревателя программы, чтобы отобразить дерево ресурсов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , зарегистрированных в этом пункте управления программой.</span><span class="sxs-lookup"><span data-stu-id="77a54-112">View the Utility Explorer Navigation Pane to see a tree view of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources in the UCP.</span></span>

 <span data-ttu-id="77a54-113">При создании новой точкой управления служебной программой также устанавливается соединение со служебной программой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="77a54-113">Creating a new UCP also connects you to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="77a54-114">Дополнительные сведения см. в статье [Создание точки управления служебной программой SQL Server (служебная программа SQL Server Utility)](create-a-sql-server-utility-control-point-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="77a54-114">For more information, see [Create a SQL Server Utility Control Point &#40;SQL Server Utility&#41;](create-a-sql-server-utility-control-point-sql-server-utility.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="77a54-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="77a54-115">See Also</span></span>
 <span data-ttu-id="77a54-116">[Служебная программа SQL Server функции и задачи](sql-server-utility-features-and-tasks.md) [Просмотр результатов Работоспособность ресурсов политики &#40;служебная программа SQL Server&#41;](view-resource-health-policy-results-sql-server-utility.md)</span><span class="sxs-lookup"><span data-stu-id="77a54-116">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) [View Resource Health Policy Results &#40;SQL Server Utility&#41;](view-resource-health-policy-results-sql-server-utility.md)</span></span>


