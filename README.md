# How to get row details by row index in Flutter DataGrid (SfDataGrid)?

In this article, we will show how to change scrollbar appearance in [Flutter DataTable](https://www.syncfusion.com/flutter-widgets/flutter-datagrid).

Initialize the [SfDataGrid](https://pub.dev/documentation/syncfusion_flutter_datagrid/latest/datagrid/SfDataGrid-class.html) widget with its necessary properties. To retrieve row details in the DataGrid, use the controller property. First, create an instance of [DataGridController](https://pub.dev/documentation/syncfusion_flutter_datagrid/latest/datagrid/DataGridController-class.html) and assign it to the DataGrid's controller property. Then, to obtain information about a specific row, call the [getRowDetails](https://pub.dev/documentation/syncfusion_flutter_datagrid/latest/datagrid/DataGridController/getRowDetails.html) method from the controller and pass the row index as a parameter.

```dart
@override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Column(
        children: [
          TextButton(
              onPressed: () {
                DataGridRowDetails? details =
                    _dataGridController.getRowDetails(4);
                if (details != null) {
                  print(details.rowType);
                  print(details.dataGridRow);
                  print(details.isSelected);
                }
              },
              child: Text('Get row details')),
          Expanded(
            child: SfDataGrid(
              source: employeeDataSource,
              controller: _dataGridController,
              columns: <GridColumn>[
                GridColumn(
                  columnName: 'id',
                  label: Container(
                    padding: EdgeInsets.all(16.0),
                    alignment: Alignment.center,
                    child: Text('ID'),
                  ),
                ),
                GridColumn(
                  columnName: 'name',
                  label: Container(
                    padding: EdgeInsets.all(8.0),
                    alignment: Alignment.center,
                    child: Text('Name'),
                  ),
                ),
                GridColumn(
                  columnName: 'designation',
                  label: Container(
                    padding: EdgeInsets.all(8.0),
                    alignment: Alignment.center,
                    child: Text('Designation'),
                  ),
                ),
                GridColumn(
                  columnName: 'salary',
                  label: Container(
                    padding: EdgeInsets.all(8.0),
                    alignment: Alignment.center,
                    child: Text('Salary'),
                  ),
                ),
              ],
            ),
          ),
        ],
      ),
    );
  }
```

You can download this example on [GitHub](https://github.com/SyncfusionExamples/How-to-get-row-details-by-row-index-in-Flutter-DataGrid).