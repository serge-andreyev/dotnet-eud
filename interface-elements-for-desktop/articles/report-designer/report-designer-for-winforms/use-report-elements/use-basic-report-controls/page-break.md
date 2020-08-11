---
title: Page Break
author: Anna Gubareva
---
# Page Break

The **Page Break** control creates a page break within the document at the control's specified position. All report content below the page break is displayed on a new page.

Drag the **Page Break** item from the [Toolbox](../../report-designer-tools/toolbox.md) onto the report's area to add this control to your report.

![](../../../../../images/eurd-win-add-page-break-to-report.png)

This control is displayed as a dashed line attached to the report's left margin.

Use the **XRPageBreak** control to insert a page break between controls within a [report band](../../introduction-to-banded-reports.md) (for example, to divide subreports so that the second subreport starts on a new page).

![](../../../../../images/eurd-win-page-break-between-subreports.png)

You can also insert a page break before or after a specific report band using the band's **Page Break** property.

![](../../../../../images/eurd-win-band-page-break-property.png)

You cannot add the **XRPageBreak** control to the following bands:
* Top Margin / Bottom Margin
* Page Header / Page Footer
* Group Header / Group Footer bands (if their **Repeat Every Page** properties are enabled)
* Vertical Header / Vertical Detail / Vertical Total