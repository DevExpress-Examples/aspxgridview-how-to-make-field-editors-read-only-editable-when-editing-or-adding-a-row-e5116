<!-- default file list -->
*Files to look at*:

* [Default.aspx](./CS/WebSite/Default.aspx) (VB: [Default.aspx](./VB/WebSite/Default.aspx))
* [Default.aspx.cs](./CS/WebSite/Default.aspx.cs) (VB: [Default.aspx.vb](./VB/WebSite/Default.aspx.vb))
<!-- default file list end -->
# ASPxGridView - How to make field editors read-only/editable when editing or adding a row
<!-- run online -->
**[[Run Online]](https://codecentral.devexpress.com/e5116/)**
<!-- run online end -->


<p>This example demonstrates how to set the editor's ReadOnly property based on the grid's state. That is, it is possible to edit a field value while adding a new row, but this editor becomes ReadOnly on an attempt to edit the existing row.</p>
<p><br>It is used the <a href="http://documentation.devexpress.com/#AspNet/DevExpressWebASPxGridViewASPxGridView_CellEditorInitializetopic"><u>ASPxGridView.CellEditorInitialize</u></a> event to implement this scenario:<br>Starting with version 14.2:</p>


```cs
protected void gridView_CellEditorInitialize(object sender, DevExpress.Web.ASPxGridViewEditorEventArgs e) {
	ASPxGridView grid = sender as ASPxGridView;
	if (e.Column.FieldName == "CategoryID")
		e.Editor.ReadOnly = !grid.IsNewRowEditing;
}
```


<p>For older versions:</p>


```cs
protected void gridView_CellEditorInitialize(object sender, DevExpress.Web.ASPxGridView.ASPxGridViewEditorEventArgs e) {
	ASPxGridView grid = sender as ASPxGridView;
	if (e.Column.FieldName == "CategoryID")
		e.Editor.ReadOnly = !grid.IsNewRowEditing;
}
```


<p> </p>

<br/>


