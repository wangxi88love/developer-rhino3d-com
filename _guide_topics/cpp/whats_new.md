---
title: What's New?
description: This brief guide outlines the new object types and features in the Rhino C/C++ SDK.
author: dale@mcneel.com, steve@mcneel.com
apis: ['C/C++']
languages: ['C/C++']
platforms: ['Windows']
categories: ['Overview']
origin: http://wiki.mcneel.com/developer/rhino/5/sdkfeatures
order: 2
keywords: ['c', 'C/C++', 'plugin']
layout: toc-guide-page
TODO: 'needs review and the original contained links to empty wiki entries.'
---

# {{ page.title }}

{{ page.description }}

## Overview

The Rhino 6.0 C++ SDK is similar to the 5.0 SDK, but also has "breaking" changes. The following document attempts to describe what has been added, what has changed, and how to deal with these changes.

## Deprecation

Obsolete functions from Rhino 5 are marked as deprecated with a message to help accomplish the same goal through alternate functions in the Rhino 6 SDK. These deprecations will generate compiler warnings when plug-in code attempts to call these functions.

Functions marked as deprecated continue to work in Rhino 6. In Rhino 7, the functions marked as deprecated in Rhino 6 will be removed.

## Additions

TODO: what has been added?

## Changes

- CRhinoDisplayPipeline::GetRhinoVP() returns a CRhinoViewport* instead of a CRhinoViewport& - there was a potential case where a null pointer dereference could occur



TODO: The following list was compiled while attempting to update C++ samples from 5.0 to 6.0. This list is currently just a series of jotted down notes and needs to be updated with information.

V5: ON_3dmView::m_target
V6: ON_3dmView::TargetPoint()

V5: CRhinoPageView::CreatePageView()
V6: CRhinoDoc::CreatePageView()

V5: ON::UnitScale(ON::inches, ON::millimeters)
V6: ON::UnitScale(ON::LengthUnitSystem::Inches, ON::LengthUnitSystem::Millimeters)

V5: ON_UnitSystem units(ON::millimeters);
V6: ON_UnitSystem units(ON::LengthUnitSystem::Millimeters);

V5: ON_TextDot::SetPoint(ON_3dPoint)
V6: ON_TextDot::SetCenterPoint(ON_3dPoint)

V5: ON_TextDot::SetTextString(const wchar_t*)
V6: ON_TextDot::SetPrimaryText(const wchar_t*)

V5: CRhinoUiDib
V6: CRhinoDib

V5: CRhinoGetPoint::DynamicDraw(HDC, CRhinoViewport&, const ON_3dPoint&)
V6: CRhinoGetPoint::DynamicDraw(CRhinoDisplayPipeline&, const ON_3dPoint&)

V5: ON_MeshParameters::Set(double, double)
V6: ON_MeshParameters(double, double)

V5: ON_DimStyle::m_dimstyle_id
V6: ON_DimStyle::Id()

CRhinoDimStyleTable::OverrideDimStyle - new function
ON_DimStyle::SetFieldOverride - enum has changed
ON_DimStyle::SetTextAlignment - enum has changed

CRhinoDisplayPipeline::DrawString - different arguments

V5: CRhinoViewport::GetPickXform
V6: CRhinoViewport::SetClippingRegionTransformation

RhinoCreateTaperedExtrude - new tolerance arguments

V5: CRhinoHatchPatternTable::FindHatchPattern
V6: CRhinoHatchPatternTable::HatchPatternFromName

RhinoCreateHatches - new tolerance argument

V5: CRhinoViewport::GetModelXform()
V5: CRhinoViewport::SetModelXform()
V6: CRhinoDisplayPipeline::PushModelTransform()
V6: CRhinoDisplayPipeline::PopModelTransform()

V5: ON_Layer::SetLayerName()
V5: ON_Layer::SetLayerIndex()
V6: ON_Layer::SetName()
V6: ON_Layer::SetIndex()

ONX_Model has changed dramatically

CRhinoDrawCallback is gone

V5: CRhinoGetObject::meshvertex_object
V6: CRhinoGetObject::meshvertex_filter

V5: ON_MeshVertexRef
V6: ON_MeshComponentRef

V5: CRhinoObjRef::MeshVertex()
V6: CRhinoObjRef::MeshComponentRef()

V5: ON_Texture::m_filename
V6: ON_Texture::m_image_file_reference

V5: CRhinoGroup::IsReference()
V6: CRhinoGroup::IsReferenceComponent()

V5: CRhinoReduceMeshProgressContext

CRhinoDisplayPipeline::Draw2dLine args have changed

V5: CRhinoViewport::DisplayMode
V6: CRhinoViewport::DisplayModeIsShaded, CRhinoViewport::View()::m_display_mode_id
Or dp.DisplayAttrs()->m_bShadeSurface

V5: CRhinoAppSettings::DefaultMaterial
V6: CRhinoMaterialTable::DefaultMaterial, CRhinoMaterialTable::AddCopyOfDefaultMaterial

CRhinoLayerTable::FindLayerFromUniqueName args changed

CRhinoViewport::GhostedShade doesn’t exist.

CRhinoFileWriteOptions::Mode doesn’t exist

V6: CRhinoDisplayPipeline::GetRhinoVP returns a pointer


V5: CRhinoObject::m_runtime_object_serial_number
V6: CRhinoObject::RuntimeSerialNumber()

V5: CRhinoEventWatcher::FontTableEvent
V6: CRhinoEventWatcher::TextStyleTableEvent

V5: ON::unit_system CRhinoDigitizerPlugIn::UnitSystem() const;
V6: ON::LengthUnitSystem CRhinoDigitizerPlugIn::UnitSystem() const;

V5: CRhinoFileWriteOptions::Mode(CRhinoFileWriteOptions::SelectedMode)
V6: CRhinoFileWriteOptions::SelectedObjectFilter()

V5: ON_OBJECT_IMPLEMENT::m_##cls##_class_id
V6: ON_OBJECT_IMPLEMENT::m_##cls##_class_rtti

V5: CRhinoApp::ActiveDoc()
V6: CRhinoDoc::FromRuntimeSerialNumber()

V5: CRhinoDialog::SetEnableDisplayCommands(bool)
V6: CRhinoDialog::SetEnableDisplayCommands(bool, unsigned int doc_sn)

V5: CRhinoDisplayConduit::Enable()
V6: CRhinoDisplayConduit::Enable(unsigned int doc_sn)

V5: ON::display_mode,  ON::DisplayMode
V6: ON_StandardDisplayModeId

V5: CRhinoGetFileDialog::open_rhino_only_dialog
V6: CRhinoGetFileDialog::open_rhino_3dm_file_dialog

V5: ON_BinaryFile archive(ON::read3dm, archive_fp);
V6: ON_BinaryFile archive(ON::archive_mode::read3dm, archive_fp);

V5: CRhinoTabbedDockBarDialog::Icon()
V6: CRhinoTabbedDockBarDialog::Icon(const CSize& sizeInPixels)

V5: CRhinoOptionsDialogPage::RunScript(CRhinoDoc&)
V6: CRhinoOptionsDialogPage::RunScript(const unsigned int rhino_doc_sn)

V5: CRhinoObjectPropertiesDialogPageEx
V6: CRhinoObjectPropertiesDialogPage