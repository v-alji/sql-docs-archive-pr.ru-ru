---
title: Сведения об олицетворении | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 42319d60-ccd0-46b8-af0b-f0968c390d8a
author: minewiskan
ms.author: owend
ms.openlocfilehash: f9226fdbe8656aecf0f9173976c67ee386040d6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728925"
---
# <a name="impersonation-information"></a><span data-ttu-id="d19e0-102">Сведения об олицетворении</span><span class="sxs-lookup"><span data-stu-id="d19e0-102">Impersonation Information</span></span>
  <span data-ttu-id="d19e0-103">Страница **Сведений об олицетворении** служит для указания учетных данных, которые будут использоваться службами Analysis Services для соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="d19e0-103">Use the **Impersonation Information** page to specify the credentials that Analysis Services will use to connect to the data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d19e0-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="d19e0-104">Options</span></span>  
 <span data-ttu-id="d19e0-105">**Использовать конкретное имя пользователя Windows и пароль**</span><span class="sxs-lookup"><span data-stu-id="d19e0-105">**Use a specific Windows user name and password**</span></span>  
 <span data-ttu-id="d19e0-106">Выберите этот параметр, чтобы объект служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] использовал учетные данные безопасности указанной пользовательской учетной записи Windows.</span><span class="sxs-lookup"><span data-stu-id="d19e0-106">Select this option to have the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object use the security credentials of a specified Windows user account.</span></span> <span data-ttu-id="d19e0-107">Заданные учетные данные будут использоваться для обработки данных, запросов ROLAP, внешних привязок, локальных кубов, моделей интеллектуального анализа данных, удаленных секций, связанных объектов и синхронизации цели с источником.</span><span class="sxs-lookup"><span data-stu-id="d19e0-107">The specified credentials will be used for processing, ROLAP queries, out-of-line bindings, local cubes, mining models, remote partitions, linked objects, and synchronization from target to source.</span></span> <span data-ttu-id="d19e0-108">Однако для инструкций расширений интеллектуального анализа данных OPENQUERY этот параметр не используется. Будут применены учетные данные не указанного, а текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="d19e0-108">However, for Data Mining Extensions (DMX) OPENQUERY statements, this option is ignored and the credentials of the current user will be used.</span></span>  
  
 <span data-ttu-id="d19e0-109">**User name**</span><span class="sxs-lookup"><span data-stu-id="d19e0-109">**User name**</span></span>  
 <span data-ttu-id="d19e0-110">Введите домен и имя учетной записи пользователя для использования выбранным объектом служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d19e0-110">Type the domain and name of the user account to be used by the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="d19e0-111">Используйте следующий формат:</span><span class="sxs-lookup"><span data-stu-id="d19e0-111">Use the following format:</span></span>  
  
 <span data-ttu-id="d19e0-112">*\<Domain name>* **\\** *\<User account name>*</span><span class="sxs-lookup"><span data-stu-id="d19e0-112">*\<Domain name>* **\\** *\<User account name>*</span></span>  
  
 <span data-ttu-id="d19e0-113">Этот параметр будет включен только в случае выбора параметра **Использовать указанные имя пользователя и пароль** .</span><span class="sxs-lookup"><span data-stu-id="d19e0-113">This option is enabled only if **Use a specific name and password** is selected.</span></span>  
  
 <span data-ttu-id="d19e0-114">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="d19e0-114">**Password**</span></span>  
 <span data-ttu-id="d19e0-115">Введите пароль учетной записи пользователя для использования выбранным объектом служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d19e0-115">Type the password of the user account to be used by the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="d19e0-116">Этот параметр будет включен только в случае выбора параметра **Использовать указанные имя пользователя и пароль** .</span><span class="sxs-lookup"><span data-stu-id="d19e0-116">This option is enabled only if **Use a specific name and password** is selected.</span></span>  
  
 <span data-ttu-id="d19e0-117">**Использовать учетную запись службы**</span><span class="sxs-lookup"><span data-stu-id="d19e0-117">**Use the service account**</span></span>  
 <span data-ttu-id="d19e0-118">Выберите этот параметр, чтобы объект служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] использовал учетные данные безопасности, связанные со службой [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , управляющей объектом.</span><span class="sxs-lookup"><span data-stu-id="d19e0-118">Select this option to have the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object use the security credentials associated with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] service that manages the object.</span></span> <span data-ttu-id="d19e0-119">Учетные данные учетной записи службы будут использоваться для обработки данных, запросов ROLAP, удаленных секций, связанных объектов и синхронизации цели с источником.</span><span class="sxs-lookup"><span data-stu-id="d19e0-119">The service account credentials will be used for processing, ROLAP queries, remote partitions, linked objects, and synchronization from target to source.</span></span> <span data-ttu-id="d19e0-120">Для инструкций расширений интеллектуального анализа данных OPENQUERY, локальных кубов и моделей интеллектуального анализа данных будут использоваться учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="d19e0-120">However, for Data Mining Extensions (DMX) OPENQUERY statements, local cubes, and mining models, the credentials of the current user will be used.</span></span> <span data-ttu-id="d19e0-121">Этот параметр не поддерживается для внешних привязок.</span><span class="sxs-lookup"><span data-stu-id="d19e0-121">This option is not supported for out-of-line bindings.</span></span>  
  
 <span data-ttu-id="d19e0-122">**Использовать учетные данные текущего пользователя**</span><span class="sxs-lookup"><span data-stu-id="d19e0-122">**Use the credentials of the current user**</span></span>  
 <span data-ttu-id="d19e0-123">Если выбран этот параметр, база данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] будет использовать учетные данные безопасности текущего пользователя для внешних привязок, DMX-инструкций OPENQUERY, локальных кубов и моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="d19e0-123">Select this option to have the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object use the security credentials of the current user for out-of-line bindings, DMX OPENQUERY, local cubes, and mining models.</span></span> <span data-ttu-id="d19e0-124">Этот параметр не поддерживается для обработки данных, запросов ROLAP, удаленных секций, связанных объектов и синхронизации цели с источником.</span><span class="sxs-lookup"><span data-stu-id="d19e0-124">This option is not supported for processing, ROLAP queries, remote partitions, linked objects, and synchronization from target to source.</span></span>  
  
 <span data-ttu-id="d19e0-125">**Следующих**</span><span class="sxs-lookup"><span data-stu-id="d19e0-125">**Inherit**</span></span>  
 <span data-ttu-id="d19e0-126">Выберите этот параметр, чтобы использовать режим работы олицетворения, определенный на том уровне базы данных, который был задан администратором сервера с помощью свойства базы данных `DataSourceImpersonation`.</span><span class="sxs-lookup"><span data-stu-id="d19e0-126">Select this option to use the impersonation behavior, defined at the database level, which has been set by the server administrator using the `DataSourceImpersonation` database property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d19e0-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="d19e0-127">See Also</span></span>  
 <span data-ttu-id="d19e0-128">[Источники данных в многомерных моделях](multidimensional-models/data-sources-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="d19e0-128">[Data Sources in Multidimensional Models](multidimensional-models/data-sources-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="d19e0-129">Поддерживаемые источники данных &#40;многомерные&#41;SSAS</span><span class="sxs-lookup"><span data-stu-id="d19e0-129">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](multidimensional-models/supported-data-sources-ssas-multidimensional.md)  
  
  
