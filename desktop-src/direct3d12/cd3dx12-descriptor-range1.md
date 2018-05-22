---
title: CD3DX12\_DESCRIPTOR\_RANGE1 structure
description: A helper structure to enable easy initialization of a D3D12\_DESCRIPTOR\_RANGE1 structure.
ms.assetid: '9D073158-5907-4D1C-8D75-72B304277DAD'
keywords: ["CD3DX12_DESCRIPTOR_RANGE1 structure"]
topic_type:
- apiref
api_name:
- CD3DX12_DESCRIPTOR_RANGE1
api_location:
- d3dx12.h
api_type:
- HeaderDef
---

# CD3DX12\_DESCRIPTOR\_RANGE1 structure

A helper structure to enable easy initialization of a [**D3D12\_DESCRIPTOR\_RANGE1**](d3d12-descriptor-range1.md) structure.

## Syntax


```C++
struct CD3DX12_DESCRIPTOR_RANGE1  : public D3D12_DESCRIPTOR_RANGE1{
   ����CD3DX12_DESCRIPTOR_RANGE1();
   ����explicit CD3DX12_DESCRIPTOR_RANGE1(const D3D12_DESCRIPTOR_RANGE1 &amp;o);
   ����CD3DX12_DESCRIPTOR_RANGE1(D3D12_DESCRIPTOR_RANGE_TYPE rangeType, UINT numDescriptors, UINT baseShaderRegister, UINT registerSpace = 0, D3D12_DESCRIPTOR_RANGE_FLAGS flags = D3D12_DESCRIPTOR_RANGE_FLAG_NONE, UINT offsetInDescriptorsFromTableStart = D3D12_DESCRIPTOR_RANGE_OFFSET_APPEND);
  void inline Init(D3D12_DESCRIPTOR_RANGE_TYPE rangeType, UINT numDescriptors, UINT baseShaderRegister, UINT registerSpace = 0, D3D12_DESCRIPTOR_RANGE_FLAGS flags = D3D12_DESCRIPTOR_RANGE_FLAG_NONE, UINT offsetInDescriptorsFromTableStart = D3D12_DESCRIPTOR_RANGE_OFFSET_APPEND);
  void static inline Init(D3D12_DESCRIPTOR_RANGE1 &amp;range, D3D12_DESCRIPTOR_RANGE_TYPE rangeType, UINT numDescriptors, UINT baseShaderRegister, UINT registerSpace = 0, D3D12_DESCRIPTOR_RANGE_FLAGS flags = D3D12_DESCRIPTOR_RANGE_FLAG_NONE, UINT offsetInDescriptorsFromTableStart = D3D12_DESCRIPTOR_RANGE_OFFSET_APPEND);
};
```



## Members

<dl> <dt>

**CD3DX12\_DESCRIPTOR\_RANGE1()**
</dt> <dd>

Creates a new, uninitialized, instance of a CD3DX12\_DESCRIPTOR\_RANGE1.

</dd> <dt>

**explicit CD3DX12\_DESCRIPTOR\_RANGE1(const D3D12\_DESCRIPTOR\_RANGE1 &o)**
</dt> <dd>

Creates a new instance of a CD3DX12\_DESCRIPTOR\_RANGE1, initialized with the contents of another [**D3D12\_DESCRIPTOR\_RANGE1**](d3d12-descriptor-range1.md) structure.

</dd> <dt>

**CD3DX12\_DESCRIPTOR\_RANGE1(D3D12\_DESCRIPTOR\_RANGE\_TYPE rangeType, UINT numDescriptors, UINT baseShaderRegister, UINT registerSpace = 0, D3D12\_DESCRIPTOR\_RANGE\_FLAGS flags = D3D12\_DESCRIPTOR\_RANGE\_FLAG\_NONE, UINT offsetInDescriptorsFromTableStart = D3D12\_DESCRIPTOR\_RANGE\_OFFSET\_APPEND)**
</dt> <dd>

Creates a new instance of a CD3DX12\_DESCRIPTOR\_RANGE1, initializing the following parameters:

[**D3D12\_DESCRIPTOR\_RANGE\_TYPE**](d3d12-descriptor-range-type.md) rangeType

UINT numDescriptors

UINT baseShaderRegister

UINT registerSpace = 0

[**D3D12\_DESCRIPTOR\_RANGE\_FLAGS**](d3d12-descriptor-range-flags.md) flags = D3D12\_DESCRIPTOR\_RANGE\_FLAG\_NONE

UINT offsetInDescriptorsFromTableStart = D3D12\_DESCRIPTOR\_RANGE\_OFFSET\_APPEND

</dd> <dt>

**inline Init(D3D12\_DESCRIPTOR\_RANGE\_TYPE rangeType, UINT numDescriptors, UINT baseShaderRegister, UINT registerSpace = 0, D3D12\_DESCRIPTOR\_RANGE\_FLAGS flags = D3D12\_DESCRIPTOR\_RANGE\_FLAG\_NONE, UINT offsetInDescriptorsFromTableStart = D3D12\_DESCRIPTOR\_RANGE\_OFFSET\_APPEND)**
</dt> <dd>

Specifies a function that initializes the following parameters:

[**D3D12\_DESCRIPTOR\_RANGE\_TYPE**](d3d12-descriptor-range-type.md) rangeType

UINT numDescriptors

UINT baseShaderRegister

UINT registerSpace = 0

[**D3D12\_DESCRIPTOR\_RANGE\_FLAGS**](d3d12-descriptor-range-flags.md) flags = D3D12\_DESCRIPTOR\_RANGE\_FLAG\_NONE

UINT offsetInDescriptorsFromTableStart = D3D12\_DESCRIPTOR\_RANGE\_OFFSET\_APPEND

</dd> <dt>

**static inline Init(D3D12\_DESCRIPTOR\_RANGE1 &range, D3D12\_DESCRIPTOR\_RANGE\_TYPE rangeType, UINT numDescriptors, UINT baseShaderRegister, UINT registerSpace = 0, D3D12\_DESCRIPTOR\_RANGE\_FLAGS flags = D3D12\_DESCRIPTOR\_RANGE\_FLAG\_NONE, UINT offsetInDescriptorsFromTableStart = D3D12\_DESCRIPTOR\_RANGE\_OFFSET\_APPEND)**
</dt> <dd>

Specifies a function that initializes the following parameters:

[**D3D12\_DESCRIPTOR\_RANGE1**](d3d12-descriptor-range1.md) &range

[**D3D12\_DESCRIPTOR\_RANGE\_TYPE**](d3d12-descriptor-range-type.md) rangeType

UINT numDescriptors

UINT baseShaderRegister

UINT registerSpace = 0

[**D3D12\_DESCRIPTOR\_RANGE\_FLAGS**](d3d12-descriptor-range-flags.md) flags = D3D12\_DESCRIPTOR\_RANGE\_FLAG\_NONE

UINT offsetInDescriptorsFromTableStart = D3D12\_DESCRIPTOR\_RANGE\_OFFSET\_APPEND

</dd> </dl>

## Requirements



|                   |                                                                                     |
|-------------------|-------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>D3dx12.h</dt> </dl> |



## See also

<dl> <dt>

[**D3D12\_DESCRIPTOR\_RANGE1**](d3d12-descriptor-range1.md)
</dt> <dt>

[Helper Structures for D3D12](helper-structures-for-d3d12.md)
</dt> </dl>

�

�




