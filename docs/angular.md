---
sidebar_position: 10
---

# Angular

## Components
- Components are responsible for a single part of the UI.
- In general, they have two main jobs.
    - Accurately display the application state to the user
    - Provide some ways that the user can manipulate the state.
- All angular applications share a root component, which is called the `app.component`.
- Components are made up of...
    - A typescript class
    - A template
    - CSS

## Templating
- String Interpolation
```html
<div>
    {{ myName }}
</div>
```
- Variables, functions, simple actions
```html
<div>
    <p>What is your favorite fruit?</p>
    <input type="text" #fruit />
    <button (click)="recordFruit(fruit)">Add Fruit</button>
</div>
```
- Attribute modification
The div will have class bough if item.purchased is true.  The curly brackets is a short-hand if statement.
```html
<div [ngClass]="{ bought: item.purchased }">
    {{ item }}
</div>
```
- ngFor
```html
<div *ngFor="let item of items">
    {{ item }}
</div>
```
- ngIf
```html
<div *ngIf="item.available === true">
    This item is available
</div>
```

## Routing

### Defining Routes
- The routes are defined in app.routing module via a list of route objects.
- A single path can be defined for each component.
- A default component can be set with the chars `**` which signifies the index route.

### Using Routes
- Then, the `<routing-outlet></routing-outlet>` module can be used to show the result of the routing.
- The `routerLink` property can be added to anchor tags so that when they are clicked, the components will be shown.
- The `routerLinkActive` property can be used to add classes to the anchor when the anchor is currently selected.

    
