# Databunding

Vamos aprender a crear un databunding lo primero es crear una app de angular ejecutando el siguiente comando:

```
npm install -g @angular/cli
```

```
ng new my-app
```

Una vez creado todo, podemos hacer un npm i por si no está los node modules, bueno sigamos, vamos a ir app.component.html y pegamos lo siguiente

```
<div class="container">
  <div class="row">
    <div class="col-xs-12">
      <ol>
        <li>Add a Input field which updates a property ('username') via Two-Way-Binding</li>
        <li>Output the username property via String Interpolation (in a paragraph below the input)</li>
        <li>Add a button which may only be clicked if the username is NOT an empty string</li>
        <li>Upon clicking the button, the username should be reset to an empty string</li>
      </ol>
      <hr>
      <label for="username">username</label>
      <input type="text" class="form-control" name="username" id="username" [(ngModel)]="username">    
      <p>{{username}}</p>  
      <button class="btn btn-primary" [disabled]="username === ''"  (click)="username = ''">Reset User</button>
    </div>
  </div>
</div>
```

Y en app.component.ts vamos a escribir lo siguiente.

```
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  username = '';
}

```

Estamos creando una variable vacia que se llama username esto nos permitira hacen el bindin ya por último vamos a app.module.ts e importamos forms.

```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms';

import { AppComponent } from './app.component';

@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule, FormsModule],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule {}

```

Por ultimo ejecutamos ng serve para probarlo.
