### Demo first app for angular 2

0.1. Install node and npm on windows
--------------------

Update npm to lastest version on windows: Run powershell as administrator

```
Set-ExecutionPolicy Unrestricted -Scope CurrentUser -Force
npm install -g npm-windows-upgrade
npm-windows-upgrade
```

0.2. Install dependency library
--------------------

```
npm install
```

If the `typings` folder doesn't show up after running npm install, you'll need to install it manually with the command:

```
npm run typings install
```

0.3: Create minimal app
----------------------

```
import { NgModule }      from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';

@NgModule({
    imports:      [ BrowserModule ]
})
export class AppModule { }
```

0.4: Create a component and add it to your application
-----------------------

create a component: `app.component.ts`:

```
import { Component } from '@angular/core';
@Component({
  selector: 'my-app',
  template: '<h1>My First Angular 2 App</h1>'
})
export class AppComponent { }
```

Add to application: `app.modules.ts`:

```
import { NgModule }      from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { AppComponent }   from './app.component';
@NgModule({
  imports:      [ BrowserModule ],
  declarations: [ AppComponent ],
  bootstrap:    [ AppComponent ]
})
export class AppModule { }
```

0.5: Start up your application
-----------------

Create the file `app/main.ts` with the following content:

```
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';
import { AppModule } from './app.module';
const platform = platformBrowserDynamic();
platform.bootstrapModule(AppModule);
```

