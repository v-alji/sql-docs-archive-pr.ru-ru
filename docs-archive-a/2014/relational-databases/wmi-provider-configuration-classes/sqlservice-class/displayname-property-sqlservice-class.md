---
title: Свойство DisplayName (класс SqlService) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- DisplayName Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- DisplayName property
ms.assetid: 49c408aa-6eb4-45cd-8d5c-60f065f24f5c
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 147fc298d6d263caf1e4ad6852d4b02f86911572
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738111"
---
# <a name="displayname-property-sqlservice-class"></a><span data-ttu-id="4e813-102">Свойство DisplayName (класс SqlService)</span><span class="sxs-lookup"><span data-stu-id="4e813-102">DisplayName Property (SqlService Class)</span></span>
  <span data-ttu-id="4e813-103">Возвращает отображаемое имя службы.</span><span class="sxs-lookup"><span data-stu-id="4e813-103">Gets the display name of the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e813-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e813-104">Syntax</span></span>  
  
```  
  
object  
.DisplayName [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="4e813-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="4e813-105">Parts</span></span>  
 <span data-ttu-id="4e813-106">*object*</span><span class="sxs-lookup"><span data-stu-id="4e813-106">*object*</span></span>  
 <span data-ttu-id="4e813-107">Объект [класса SqlService](sqlservice-class.md) , представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="4e813-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="4e813-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4e813-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="4e813-109">Строковое значение, определяющее отображаемое имя службы.</span><span class="sxs-lookup"><span data-stu-id="4e813-109">A string value that specifies the display name of the service.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e813-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="4e813-110">Remarks</span></span>  
 <span data-ttu-id="4e813-111">Максимальная длина этой строки равна 256 символам.</span><span class="sxs-lookup"><span data-stu-id="4e813-111">This string has a maximum length of 256 characters.</span></span> <span data-ttu-id="4e813-112">Имя с учетом регистра сохраняется в диспетчере конфигурации [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4e813-112">The name is case-preserved in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="4e813-113">Но сравнения отображаемых имен всегда выполняются без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="4e813-113">However, display name comparisons are always case-insensitive.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e813-114">Пример</span><span class="sxs-lookup"><span data-stu-id="4e813-114">Example</span></span>  
  
```  
mysqlservice.DisplayName = "Atdisk"  
```  
  
## <a name="see-also"></a><span data-ttu-id="4e813-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="4e813-115">See Also</span></span>  
 <span data-ttu-id="4e813-116">[Запуск и остановка служб](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="4e813-116">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
