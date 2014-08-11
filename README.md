<div>
  <h3>{{user.name}}</h3>

  <img ng-src="http://www.gravatar.com/avatar/{{user.gravatar_id}}" title="{{user.name}}" />
  <hr>Order:
  <select ng-model="repoSortOrder">
    <option value="+name">Name(ascending)</option>
    <option value="-name">Name (descending)</option>
    <option value="-stargazers_count">Stars</option>
    <option value="+language">Language</option>
  </select>
</div>


<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Stars</th>
      <th>Language</th>
    </tr>
  </thead>
  <tbody>
    <tr ng-repeat="repo in repos | orderBy:repoSortOrder">
      <td>{{repo.name}}</td>
      <td>{{repo.stargazers_count | number}}</td>
      <td>{{repo.language}}</td>
    </tr>
  </tbody>
</table>