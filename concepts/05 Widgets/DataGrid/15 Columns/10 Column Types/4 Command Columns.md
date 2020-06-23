Command columns are used for interaction. The **DataGrid** provides the following command columns.

- **Editing Column**        
Contains editing controls. Appears when [editing](/api-reference/10%20UI%20Widgets/dxDataGrid/1%20Configuration/editing '/Documentation/ApiReference/UI_Widgets/dxDataGrid/Configuration/editing/') is allowed and depends on the [editing mode](/api-reference/10%20UI%20Widgets/GridBase/1%20Configuration/editing/mode.md '/Documentation/ApiReference/UI_Widgets/dxDataGrid/Configuration/editing/#mode').

- **Adaptive Column**       
Contains buttons that expand adaptive detail rows. Appears if [columnHidingEnabled](/api-reference/10%20UI%20Widgets/GridBase/1%20Configuration/columnHidingEnabled.md '/Documentation/ApiReference/UI_Widgets/dxDataGrid/Configuration/#columnHidingEnabled') is **true** or [hidingPriority](/api-reference/10%20UI%20Widgets/GridBase/1%20Configuration/columns/hidingPriority.md '/Documentation/ApiReference/UI_Widgets/dxDataGrid/Configuration/columns/#hidingPriority') is set for at least one column and only when certain columns do not fit into the screen or container size.

- **Selection Column**    
Contains check boxes that select rows. Appears if **selection**.[mode](/api-reference/10%20UI%20Widgets/GridBase/1%20Configuration/selection/mode.md '/Documentation/ApiReference/UI_Widgets/dxDataGrid/Configuration/selection/#mode') is *"multiple"* and [showCheckBoxesMode](/api-reference/10%20UI%20Widgets/dxDataGrid/1%20Configuration/selection/showCheckBoxesMode.md '/Documentation/ApiReference/UI_Widgets/dxDataGrid/Configuration/selection/#showCheckBoxesMode') differs from *"none"*.


![DevExtreme HTML5 JavaScript DataGrid CommandColumns EditingColumn AdaptiveColumn](/images/DataGrid/Command_Columns.png)

You can relocate or resize the command columns by changing their **visibleIndex** and **width** options. For this, call the [columnOption(id, optionName, optionValue)](/api-reference/10%20UI%20Widgets/GridBase/3%20Methods/columnOption(id_optionName_optionValue).md '/Documentation/ApiReference/UI_Widgets/dxDataGrid/Methods/#columnOptionid_optionName_optionValue') method as shown by the following code.

---
##### jQuery

    <!--JavaScript-->
    var dataGrid = $("#dataGridContainer").dxDataGrid("instance");

    // places the selection column after all columns
    dataGrid.columnOption("command:select", "visibleIndex", 999);

    // changes the width of the selection column to 50 pixels
    dataGrid.columnOption("command:select", "width", 50);

    // places the editing column before all others
    dataGrid.columnOption("command:edit", "visibleIndex", -2);

    // changes the width of the editing column to 200 pixels
    dataGrid.columnOption("command:edit", "width", 200);

    // places the adaptive column before all data columns, but after the editing column
    dataGrid.columnOption("command:adaptive", "visibleIndex", -1);

    // changes the width of the adaptive column to 80 pixels
    dataGrid.columnOption("command:adaptive", "width", 80);

##### Angular

    <!--TypeScript-->
    import { ..., ViewChild } from '@angular/core';
    import { DxDataGridModule, DxDataGridComponent } from 'devextreme-angular';
    // ...
    export class AppComponent {
        @ViewChild(DxDataGridComponent) dataGrid: DxDataGridComponent;
        modifySelectionColumn () {
            // places the selection column after all columns
            this.dataGrid.instance.columnOption("command:select", "visibleIndex", 999);

            // changes the width of the selection column to 50 pixels
            this.dataGrid.instance.columnOption("command:select", "width", 50);
        }
        modifyEditingColumn () {
            // places the editing column before all others
            this.dataGrid.instance.columnOption("command:edit", "visibleIndex", -2);

            // changes the width of the editing column to 200 pixels
            this.dataGrid.instance.columnOption("command:edit", "width", 200);
        }
        modifyAdaptiveColumn () {
            // places the adaptive column before all data columns, but after the editing column
            this.dataGrid.instance.columnOption("command:adaptive", "visibleIndex", -1);

            // changes the width of the adaptive column to 80 pixels
            this.dataGrid.instance.columnOption("command:adaptive", "width", 80);
        }
    }
    @NgModule({
        imports: [
            // ...
            DxDataGridModule
        ],
        // ...
    })
    
---

You can also customize cells of command columns using the [onCellPrepared](/api-reference/10%20UI%20Widgets/dxDataGrid/1%20Configuration/onCellPrepared.md '/Documentation/ApiReference/UI_Widgets/dxDataGrid/Configuration/#onCellPrepared') function. To distinguish cells of a command column from others, check the argument's **column.command** field for the *"edit"*, *"adaptive"* or *"select"* value.

---
##### jQuery

    <!--JavaScript-->$(function() {
        $("#dataGridContainer").dxDataGrid({
            onCellPrepared: function(e) {
                if (e.rowType == "data") {
                    var cell = e.cellElement;
                    switch (e.column.command) {
                        case "edit":
                            // ...
                            break;
                        case "adaptive":
                            // ...
                            break;
                        case "select";
                            // ...
                            break;
                    }
                }
            }
        });
    });

##### Angular

    <!--TypeScript-->
    import { DxDataGridModule } from 'devextreme-angular';
    // ...
    export class AppComponent {
        onCellPrepared (e) {
            if (e.rowType == "data") {
                let cell = e.cellElement;
                switch (e.column.command) {
                    case "edit":
                        // ...
                        break;
                    case "adaptive":
                        // ...
                        break;
                    case "select";
                        // ...
                        break;
                }
            }
        };
    }
    @NgModule({
        imports: [
            // ...
            DxDataGridModule
        ],
        // ...
    })

    <!--HTML-->
    <dx-data-grid ...
        (onCellPrepared)="onCellPrepared($event)">
    </dx-data-grid>
    
---

#include common-demobutton with {
    url: "https://js.devexpress.com/Demos/WidgetsGallery/Demo/DataGrid/CustomizeCommandColumns/jQuery/Light/"
}

[tags] dataGrid, data grid, column types, command columns, editing column, adaptive column, selection column