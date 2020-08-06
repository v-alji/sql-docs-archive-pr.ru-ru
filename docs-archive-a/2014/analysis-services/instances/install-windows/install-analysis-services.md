---
title: Установка Analysis Services в табличном режиме | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: cd6ac80d-b735-4e3e-a024-489f1409ad33
author: minewiskan
ms.author: owend
ms.openlocfilehash: a677fd7770f646067cafb8fedf6d3705ccf2de3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729925"
---
# <a name="install-analysis-services-in-tabular-mode"></a><span data-ttu-id="d9bd4-102">Установка служб Analysis Services в табличном режиме</span><span class="sxs-lookup"><span data-stu-id="d9bd4-102">Install Analysis Services in Tabular Mode</span></span>
  <span data-ttu-id="d9bd4-103">Если службы Analysis Services устанавливаются для использования новых функций табличных моделей, необходимо устанавливать их в серверном режиме с поддержкой соответствующего типа модели.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-103">If you are installing Analysis Services to use the new tabular modeling features, you must install Analysis Services in a server mode that supports that type of model.</span></span> <span data-ttu-id="d9bd4-104">Серверный режим — табличный, он настраивается во время установки.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-104">The server mode is Tabular, and it is configured during installation.</span></span>  
  
 <span data-ttu-id="d9bd4-105">После установки сервера в этом режиме можно использовать его для размещения решений, создаваемых в конструкторе табличных моделей.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-105">After you install the server in this mode, you can use it host solutions that you build in tabular model designer.</span></span> <span data-ttu-id="d9bd4-106">Сервер в табличном режиме необходим, если требуется сетевой доступ к данным табличной модели.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-106">A tabular mode server is required if you want tabular model data access over the network.</span></span>  
  
 <span data-ttu-id="d9bd4-107">Табличный режим можно задать в мастере установки или в программе установки из командой строки.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-107">You can specify Tabular mode in the Installation Wizard or in a command line setup.</span></span> <span data-ttu-id="d9bd4-108">В приведенных ниже разделах описан каждый из этих способов.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-108">The following sections describe each approach.</span></span>  
  
## <a name="installation-wizard"></a><span data-ttu-id="d9bd4-109">Мастер установки</span><span class="sxs-lookup"><span data-stu-id="d9bd4-109">Installation Wizard</span></span>  
 <span data-ttu-id="d9bd4-110">В следующем списке приведены страницы в мастере установки SQL Server, используемые при установке служб Analysis Services в табличном режиме.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-110">The following list shows you which pages in the SQL Server Installation wizard are used to install Analysis Services in Tabular mode:</span></span>  
  
1.  <span data-ttu-id="d9bd4-111">Выберите **Службы Analysis Services** в дереве компонентов в программе установки.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-111">Select **Analysis Services** from the Feature Tree in Setup.</span></span>  
  
     <span data-ttu-id="d9bd4-112">![Дерево компонентов установки со службами Analysis Services](../../../sql-server/install/media/ssas-setupas.gif "Дерево компонентов установки со службами Analysis Services")</span><span class="sxs-lookup"><span data-stu-id="d9bd4-112">![Setup feature tree showing Analsyis Services](../../../sql-server/install/media/ssas-setupas.gif "Setup feature tree showing Analsyis Services")</span></span>  
  
2.  <span data-ttu-id="d9bd4-113">На странице Конфигурация Analysis Services убедитесь, что выбран **табличный режим**.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-113">On the Analysis Services Configuration page, be sure to select **Tabular Mode**.</span></span>  
  
     <span data-ttu-id="d9bd4-114">![Страница установки с параметрами конфигурации служб Analysis Services](../../../sql-server/install/media/ssas-setupasconfig.gif "Страница установки с параметрами конфигурации служб Analysis Services")</span><span class="sxs-lookup"><span data-stu-id="d9bd4-114">![Setup page with Analysis Services config options](../../../sql-server/install/media/ssas-setupasconfig.gif "Setup page with Analysis Services config options")</span></span>  
  
 <span data-ttu-id="d9bd4-115">Табличный режим использует подсистему VertiPaq аналитики в памяти xVelocity, которая является хранилищем по умолчанию для табличных моделей, развертываемых в службах Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-115">Tabular mode uses the xVelocity in-memory analytics engine (VertiPaq), which is the default storage for tabular models that you deploy to Analysis Services.</span></span> <span data-ttu-id="d9bd4-116">После развертывания решений табличных моделей на сервере можно выборочно настроить в табличных решениях использование дискового хранилища DirectQuery в качестве альтернативы хранилищу, размещенному в оперативной памяти.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-116">After you deploy tabular model solutions to the server, you can selectively configure tabular solutions to use DirectQuery disk storage as an alternative to memory-bound storage.</span></span>  
  
## <a name="command-line-setup"></a><span data-ttu-id="d9bd4-117">Установка из командной строки</span><span class="sxs-lookup"><span data-stu-id="d9bd4-117">Command Line Setup</span></span>  
 <span data-ttu-id="d9bd4-118">В программе установки SQL Server предусмотрен новый параметр (`ASSERVERMODE`), указывающий режим сервера.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-118">SQL Server Setup includes a new parameter (`ASSERVERMODE`) that specifies the server mode.</span></span> <span data-ttu-id="d9bd4-119">В приведенном ниже примере показана установка служб Analysis Services в табличном режиме сервера из командной строки.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-119">The following example illustrates a command line setup that installs Analysis Services in Tabular server mode.</span></span>  
  
```  
  
Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /FEATURES=AS /ASSERVERMODE=TABULAR /INSTANCENAME=ASTabular /INDICATEPROGRESS/ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
```  
  
 <span data-ttu-id="d9bd4-120">Значение `INSTANCENAME` должно иметь длину менее 17 символов.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-120">`INSTANCENAME` must be less than 17 characters.</span></span>  
  
 <span data-ttu-id="d9bd4-121">Все заполнители значений учетных записей должны быть заменены на действительные учетные записи и пароли.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-121">All placeholder account values must be replaced with valid accounts and password.</span></span>  
  
 <span data-ttu-id="d9bd4-122">Такие средства, как среда SQL Server Management Studio или [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], не устанавливаются при использовании приведенного примера синтаксиса командной строки.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-122">Tools such as SQL Server Management Studio or [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] are not installed using the example command line syntax that is provided.</span></span> <span data-ttu-id="d9bd4-123">Дополнительные сведения о добавлении компонентов см. [в разделе Install SQL Server 2014 из командной строки](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="d9bd4-123">For more information about adding features, see [Install SQL Server 2014 from the Command Prompt](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span></span>  
  
 <span data-ttu-id="d9bd4-124">Значение `ASSERVERMODE` учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-124">`ASSERVERMODE` is case-sensitive.</span></span>  <span data-ttu-id="d9bd4-125">Все значения должны задаваться в верхнем регистре.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-125">All values must be expressed in upper case.</span></span> <span data-ttu-id="d9bd4-126">В следующей таблице приведены допустимые значения параметра `ASSERVERMODE`.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-126">The following table describes the valid values for `ASSERVERMODE`.</span></span>  
  
|<span data-ttu-id="d9bd4-127">Значение</span><span class="sxs-lookup"><span data-stu-id="d9bd4-127">Value</span></span>|<span data-ttu-id="d9bd4-128">Описание</span><span class="sxs-lookup"><span data-stu-id="d9bd4-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d9bd4-129">MULTIDIMENSIONAL</span><span class="sxs-lookup"><span data-stu-id="d9bd4-129">MULTIDIMENSIONAL</span></span>|<span data-ttu-id="d9bd4-130">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-130">This is the default value.</span></span> <span data-ttu-id="d9bd4-131">Если не задать значение `ASSERVERMODE`, сервер будет установлен в многомерном режиме.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-131">If you do not set `ASSERVERMODE`, the server is installed in Multidimensional server mode.</span></span>|  
|<span data-ttu-id="d9bd4-132">POWERPIVOT</span><span class="sxs-lookup"><span data-stu-id="d9bd4-132">POWERPIVOT</span></span>|<span data-ttu-id="d9bd4-133">Это значение является необязательным.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-133">This value is optional.</span></span> <span data-ttu-id="d9bd4-134">На практике, если задан параметр `ROLE`, то режим сервера автоматически получает значение 1, что делает `ASSERVERMODE` необязательным в установке PowerPivot для SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-134">In practice, if you set the `ROLE` parameter, the server mode is automatically set to 1, making `ASSERVERMODE` optional for a PowerPivot for SharePoint installation.</span></span> <span data-ttu-id="d9bd4-135">Дополнительные сведения см. [в статье Установка PowerPivot из командной строки](../../../sql-server/install/install-powerpivot-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="d9bd4-135">For more information, see [Install PowerPivot from the Command Prompt](../../../sql-server/install/install-powerpivot-from-the-command-prompt.md).</span></span>|  
|<span data-ttu-id="d9bd4-136">TABULAR</span><span class="sxs-lookup"><span data-stu-id="d9bd4-136">TABULAR</span></span>|<span data-ttu-id="d9bd4-137">Это значение является обязательным при установке служб Analysis Services в табличном режиме из командной строки.</span><span class="sxs-lookup"><span data-stu-id="d9bd4-137">This value is required if you are installing Analysis Services in Tabular mode using command line setup.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d9bd4-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="d9bd4-138">See Also</span></span>  
 <span data-ttu-id="d9bd4-139">[Определение режима работы сервера для экземпляра Analysis Services](../determine-the-server-mode-of-an-analysis-services-instance.md) </span><span class="sxs-lookup"><span data-stu-id="d9bd4-139">[Determine the Server Mode of an Analysis Services Instance](../determine-the-server-mode-of-an-analysis-services-instance.md) </span></span>  
 <span data-ttu-id="d9bd4-140">[Настройка доступа в памяти или DirectQuery для базы данных табличной модели](../../tabular-models/enable-directquery-mode-in-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="d9bd4-140">[Configure In-Memory or DirectQuery Access for a Tabular Model Database](../../tabular-models/enable-directquery-mode-in-ssms.md) </span></span>  
 [<span data-ttu-id="d9bd4-141">Табличное моделирование &#40;табличные&#41;SSAS</span><span class="sxs-lookup"><span data-stu-id="d9bd4-141">Tabular Modeling &#40;SSAS Tabular&#41;</span></span>](../../tabular-models/tabular-models-ssas.md)  
  
  
