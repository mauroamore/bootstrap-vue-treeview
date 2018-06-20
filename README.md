
> A treeview component for [Bootstrap](https://getbootstrap.com/) and [Vue.js 2.0+](https://vuejs.org/)

![Bootstrap-Vue-Treeview Screenshot](https://raw.githubusercontent.com/kamil-lip/bootstrap-4-vue-treeview/master/screenshot.png)
## Features
- Drag & drop nodes
- Context menu

## Installation
```bash
npm install --save bootstrap-vue-treeview
```
## Getting started

### Webpack
If you use Webpack bundler (recommended) you can import component and register it locally:

```javascript
import { bTreeView } from 'bootstrap-vue-treeview'
[...]
components: {
	bTreeView
},
```
or globally using plugin:
```javascript
import BootstrapVueTreeview from 'bootstrap-vue-treeview'
Vue.use(BootstrapVueTreeview)
```

Now you can you the treeview component in your code:
```html
<b-tree-view data="treeData"></b-tree-view>
```
```javascript
export default {
  data() {
    return {
      treeData: [{"id": 2, "name": "Venus" , "children": [{"id": 3, "name": "Neptune"}, {"id": 4, "name": "Stratus"} ] } ]
    }
  }
}
```

## API

### BTreeView
#### 1. Props

| Prop             | Type          | Description            | Default value  | Required |
| :--------------- |:--------------|:-----------------------|:--------------|:------|
| data             | Array         | Tree data                      | - | Yes |
| nodeKeyProp      | String        | Name of the property containing unique node key | "id" | No |
| nodeChildrenProp | String        | Where to look for node children | "children" | No
| nodeLabelProp    | String        | Name of the property containing node label | "children" | No
| nodesDraggable   | Boolean       | Enable/disable drag & drop feature | false | No
| contextMenu      | Boolean       | Enable/disable context menu | true | No
| contextMenuItems | Array         | Context menu items | [ { code: 'DELETE_NODE', label: 'Delete node' } ] | No

#### 2. Events

| Event name            | Description                                                                                                                 | Parameters                                |
|-----------------------|-----------------------------------------------------------------------------------------------------------------------------|-------------------------------------------|
| nodeSelect            | Triggered every time a node is selected/deselected. Check second parameter to verify if the node was selected or deselected | BTreeNode object, isSelected              |
| contextMenuItemSelect | Triggered every time a context menu item was clicked.                                                                       | BContextMenuItem object, BTreeNode object |
|                       |                                                                                                                             |                                           |