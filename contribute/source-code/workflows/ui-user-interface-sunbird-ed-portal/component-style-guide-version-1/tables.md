# Tables

Tables are a fundamental element of the Sunbird-Ed portal's design, used for presenting structured data in an organized and user-friendly manner. Our tables are designed for clarity, consistency, and ease of use, ensuring that users can efficiently access and understand the information presented. For more information please refer to this link [https://sunbird-ed.github.io/sunbird-style-guide/dist/#/tables](https://sunbird-ed.github.io/sunbird-style-guide/dist/#/tables)

<figure><img src="../../../../../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>

```html
<div class="sb-table-responsive-div">
  <div class="sb-table-container">
    <table class="sb-table sb-table-striped sb-table-sortable sb-table-fixed sb-table-course-dashboard">
      <thead>
        <tr>
          <th class="sb-sort-icon ascending descending">External ID</th>
          <th class="sb-sort-icon ascending descending">User Name</th>
          <th class="sb-sort-icon ascending descending">Organisation Name</th>
          <th class="sb-sort-icon ascending descending">Enrolled On</th>
          <th class="sb-sort-icon ascending descending">Progress</th>
          <th class="sb-sort-icon ascending descending">Certificate Status</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td data-label="Name">177402120</td>
          <td data-label="Age">Course User 100</td>
          <td data-label="Age">Sunbird QA Tenant</td>
          <td data-label="Age">30/07/19</td>
          <td data-label="Age">100%</td>
          <td data-label="Job"><span class="sb-label sb-label-table sb-label-success-0">Issued</span></td>
        </tr>
        <tr>
            <td data-label="Name">177402120</td>
            <td data-label="Age">Course User 100</td>
            <td data-label="Age">Sunbird QA Tenant</td>
            <td data-label="Age">30/07/19</td>
            <td data-label="Age">100%</td>
            <td data-label="Job">N/A</td>
        </tr>
      </tbody>
    </table>
  </div>
</div>  
```
