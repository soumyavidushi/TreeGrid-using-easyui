# hello-world
Creating New Repository


To Track unsaved changes of a form, we can use isDirty flag but isDirty flag come true even if we don't make any change as it consideres form load also a change.
To fix this issue, on form load we should change the form fields original value to fom field's value like below.

var form = formPane.getForm();
var formFieldCollection = form.getFields();
var formItems = formFieldCollection.items;

Ext.Array.each(formItems, function(ite, index, fields){
  item.originalValue = item.getValue() || item.value;
});

form.isDirty() // will give false now and will give true only if we modify anything
