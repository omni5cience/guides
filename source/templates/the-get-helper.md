## The `{{get}}` Helper

The `{{get}}` helper is useful when you need to access properties on an object using a dynamic key.

For example, to create a table with dynamic columns:

```handlebars
<table>

  <thead>
    <tr>
      {{#each fields as |field|}}
        <th>{{field}}</th>
      {{/each}}
    </tr>
  </thead>

  <tbody>
    {{#each people as |person|}}
      <tr>
        {{#each fields as |field|}}
          <td>{{get person field}}</td>
        {{/each}}
      </tr>
    {{/each}}
  </tbody>

</table>
```

The `{{get}}` helper can also be used with the `{{input}}` helper to allow you to edit a field. You need to use the `{{mut}}` helper to achieve this:

```handlebars
<div>
  <label>{{fieldName}}</labe>
  {{input value=(mut (get person fieldKey)) type='text'}}
</div>
```
