---
title: srv_willconvert (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_willconvert
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_willconvert
ms.assetid: 6f4db5fd-215a-461c-95e4-17697852733e
author: rothja
ms.author: jroth
ms.openlocfilehash: 0b9adfbd2a73b30cbfc0229b7942f79d3ddc1a82
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751011"
---
# <a name="srv_willconvert-extended-stored-procedure-api"></a><span data-ttu-id="34d27-102">srv_willconvert (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="34d27-102">srv_willconvert (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="34d27-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="34d27-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="34d27-104">Определяет, доступно ли конкретное преобразование типов данных в библиотеке ODS.</span><span class="sxs-lookup"><span data-stu-id="34d27-104">Determines whether a specific data type conversion is available within the ODS Library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34d27-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34d27-105">Syntax</span></span>  
  
```  
  
BOOL srv_willconvert (  
int  
srctype  
,  
int  
desttype   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="34d27-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="34d27-106">Arguments</span></span>  
 <span data-ttu-id="34d27-107">*srctype*</span><span class="sxs-lookup"><span data-stu-id="34d27-107">*srctype*</span></span>  
 <span data-ttu-id="34d27-108">Указывает тип преобразуемых данных.</span><span class="sxs-lookup"><span data-stu-id="34d27-108">Indicates the data type of the data to be converted.</span></span> <span data-ttu-id="34d27-109">Этот параметр может иметь любой из типов данных API-интерфейса расширенных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="34d27-109">This parameter can be any of the Extended Stored Procedure API data types.</span></span>  
  
 <span data-ttu-id="34d27-110">*desttype*</span><span class="sxs-lookup"><span data-stu-id="34d27-110">*desttype*</span></span>  
 <span data-ttu-id="34d27-111">Указывает тип данных, в который преобразуются исходные данные.</span><span class="sxs-lookup"><span data-stu-id="34d27-111">Indicates the data type to which the source data is converted.</span></span> <span data-ttu-id="34d27-112">Этот параметр может иметь любой из типов данных API-интерфейса расширенных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="34d27-112">This parameter can be any of the Extended Stored Procedure API data types.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="34d27-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="34d27-113">Returns</span></span>  
 <span data-ttu-id="34d27-114">Значение TRUE, если преобразование типов данных поддерживается, значение FALSE, если преобразование типов данных не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="34d27-114">TRUE if the data type conversion is supported; FALSE if the data type conversion is not supported.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34d27-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="34d27-115">Remarks</span></span>  
 <span data-ttu-id="34d27-116">Описание каждого типа данных см. в разделе [Типы данных (интерфейс API расширенных хранимых процедур)](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="34d27-116">For a description of each data type, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="34d27-117">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="34d27-117">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="34d27-118">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="34d27-118">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34d27-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="34d27-119">See Also</span></span>  
 [<span data-ttu-id="34d27-120">srv_convert (интерфейс API расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="34d27-120">srv_convert &#40;Extended Stored Procedure API&#41;</span></span>](srv-convert-extended-stored-procedure-api.md)  
  
  
