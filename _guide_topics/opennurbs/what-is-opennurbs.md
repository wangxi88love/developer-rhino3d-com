---
title: What is openNURBS?
description: This guide gives an overview of the openNURBS toolkit.
authors: ['Dale Lear']
author_contacts: ['dalelear']
sdk: ['openNURBS']
languages: ['C/C++']
platforms: ['Windows', 'Mac']
categories: ['Overview']
origin: http://wiki.mcneel.com/developer/opennurbs/faq
order: 1
keywords: ['openNURBS', 'overview']
layout: toc-guide-page
---

## Overview

The openNURBS Initiative provides CAD, CAM, CAE, and computer graphics software developers the tools to accurately transfer 3-D geometry between applications.

The openNURBS Toolkit consists of C++ source code for a library that will read and write openNURBS 3D model files (*.3dm*).  More than 400 software development teams and applications, including *Rhinoceros®*, exchange 3D models using the openNURBS (*.3dm*) file format.

The openNURBS Toolkit reads and writes all Rhino 3DM files. Additionally, the openNURBS Toolkit provides NURBS evaluation tools and elementary geometric and 3D view manipulation tools.

Unlike other open development initiatives, alliances, or consortia:

- Commercial use is encouraged.
- The tools, support, and membership are free.
- There are no restrictions. Neither copyright nor copyleft restrictions apply.
- No contribution of effort or technology is required from the members, although it is encouraged.

The openNURBS Toolkit is intended for C++ and .NET programmers.  The toolkit includes complete source code to create a library that will read and write 3DM files.  The toolkit also includes source code for several example programs.

## Details

The tools provided by openNURBS include:

- [Rhino3dmIO .NET Tookit]({{ site.baseurl }}/guides/opennurbs/what-is-rhino3dmio) .NET Package distributed as a NuGet package.  This contains assemblies to create and interpret OpenNurbs geometry.  Also, use this to read/write the Rhino 3DM file format.
- [openNURBS C++ source SDK](https://www.rhino3d.com/download/openNURBS/6/release) - the original cross platform SDK.
- [Sample 3D files](http://download.rhino3d.com/openNURBS/6/opennurbs6samples)
- Quality assurance and revision control.
- Technical support.


## Limitations

Although the openNURBS toolkit appears to be a full-featured geometry library, it is not.  The toolkit does not include a number of important features, including:

- Closest point calculations
- Intersection calculations
- Surface tessellation (meshing)
- Interpolation
- Booleans
- Area and mass property calculations
- Other miscellaneous geometry calculations

openNURBS is an open source toolkit for only reading and writing 3DM models.  Our full-featured development platform is *Rhinoceros®*.  All of the above features are found in the Rhino SDKs, the toolkit used to build plugins for Rhino.

## Who is funding the openNURBS Initiative and why?

Robert McNeel & Associates.  They feel that the 3D market is stifled because of the inability to reliably transfer 3D geometry between applications.  The problem is too big for us to solve alone.  By funding the operating cost of openNURBS, others will get involved in the toolkit design and development.  It will be a much cheaper and effective way to solve the problem.

---

## Related Topics

- [openNURBS Migration Guide]({{ site.baseurl }}/guides/opennurbs/migration-guide)
- [openNURBS Latest Release Notes]({{ site.baseurl }}/guides/opennurbs/latest-release-notes)
