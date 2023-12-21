# INDEX
## インストール
```
npm i -g @angular/cli@16.2.10
```
```
npm uninstall -g @angular/cli
```
```
npm cache clean --force
```
```
ng new my-app(nombre de aplicacion)</p>
```

## モジュールの作成
```
ng generate module nombre-del-modulo
ng g m nombre-del modulo
```
```
import{ NgModule } from '@angular/core';
import { CommonModule } from '@angular/common'
import { MiComponente } from './mi-componente.component'

@NgModule({<br>
    declarations: [MiComponente],
    imports: [CommonModule],
    exports: [MiComponente]
})

export class MiModulo {}
```
  
## コンポーネントの作成
```
ng generate component nombre-del componente
ng g c nombre-del componente
```

```
npm start<br>
```
**Actively supported versions**
https://angular.io/guide/versions
Node.js
```
nvm install 18.10.0 // to install the version of node.js I wanted
nvm use 18.10.0  // use the installed version
```
Angular (Downgrade @angular-devkit/build-angular)
```
npm list @angular-devkit/build-angular
npm install @angular-devkit/build-angular@16.2.10 --save-dev
```

http://localhost:4200/


## One Way Binding コントローラーからビュー
## One way Binding　ビューからコントローラー
## Two Way Binding
## NgIf
## NgFor
## Pipe
## Router Outlet
## Path
## @Input
親　⇒　子  
1.子コンポーネントに @Input プロパティを定義  
![Captura desde 2023-12-21 10-01-39](https://github.com/naopeke/Angular_Commands/assets/143800388/04df3da9-c5e2-487f-b77c-7a89d7b0dcd7)
  
2.親コンポーネントから子コンポーネントにデータを渡す  
![Captura desde 2023-12-21 10-01-56](https://github.com/naopeke/Angular_Commands/assets/143800388/22c7b30f-4e72-46fb-9de6-3c301c021c1c)  
  
## @Output
子　⇒　親
1.子コンポーネントに @Output プロパティを定義  
![Captura desde 2023-12-21 10-08-34](https://github.com/naopeke/Angular_Commands/assets/143800388/d853f75c-680a-4051-99b7-0bd987629e55)  
  
2.親コンポーネントでイベントを受け取る  
![Captura desde 2023-12-21 10-08-52](https://github.com/naopeke/Angular_Commands/assets/143800388/98417bbd-e522-4307-992a-222e4c3259bb)

## EventEmitter
## Bootstrap
