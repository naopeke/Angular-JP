# INDEX
[](#)
1.[インストール](#インストール)  
2.[モジュールの作成](#モジュールの作成)  
3.[コンポーネントの作成](#コンポーネントの作成)  
4.[ダウングレード](#ダウングレード)  
5.[ルーティング](#ルーティング)  
6.[文字列補間（単方向バインディング）](#文字列補間単方向バインディング)  
7.[プロパティバインディング（単方向バインディング）](#プロパティバインディング単方向バインディング)  
8.[（イベントバインディング）単方向バインディング](#イベントバインディング)  
8.[双方向バインディング](#双方向バインディング)  
9.[](#)  
10.[](#)  

## NgIf
## NgFor
## Pipe
## Router Outlet
## Path
## @Input

One Way Binding コントローラーからビュー

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
http://localhost:4200/  
  
## ダウングレード
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

## ルーティング
異なるビューやコンポーネントをナビゲーションバーのURLに基づいて表示するための仕組み  
1.ルーティングモジュールの作成: 多くのプロジェクトでは、ルーティングを管理するために専用のモジュール（通常は AppRoutingModule）を作成  
```
ng generate module app-routing --flat --module=app
```
2.ルートの定義  
![Captura desde 2023-12-21 12-18-18](https://github.com/naopeke/Angular-JP/assets/143800388/c8b9fb42-b1b3-4c43-a48e-1cbba09f6d50)  

3.<router-outlet> の使用: 通常は app.component.html）に <router-outlet> を配置  
![Captura desde 2023-12-21 12-18-37](https://github.com/naopeke/Angular-JP/assets/143800388/9ab8b155-cbaf-4168-a6c6-6e70348c4e6f)  
  
4.ナビゲーションリンクの設定: routerLink ディレクティブを使って、異なるルートへのナビゲーションリンクを設定  
![Captura desde 2023-12-21 12-18-57](https://github.com/naopeke/Angular-JP/assets/143800388/28963912-6a6b-4ce1-8f65-9fcca8945cbc)
  
## 文字列補間（単方向バインディング）
One Way Binding コントローラーからビュー  
二重中括弧 {{ }} を使って、コンポーネントの TypeScript クラスからテンプレート（HTML）にデータをバインド  
```
<h1>{{expression}}</h1>
<img src="{{expression}}" />
<div [class]="expression" ></div>
<img [bind-src]="expression" />
```
![Captura desde 2023-12-21 12-09-38](https://github.com/naopeke/Angular-JP/assets/143800388/15e99fe4-d88e-4934-809d-7d9f286cce13)  
  
文字列の連結、算術演算、メソッドの呼び出しなども可能  
![Captura desde 2023-12-21 12-09-49](https://github.com/naopeke/Angular-JP/assets/143800388/3517b9f8-9c9c-4743-94de-7b2d66087a4e)  

## プロパティバインディング（単方向バインディング）
One Way Binding コントローラーからビュー  
コンポーネントのクラスプロパティとテンプレート内の HTML 要素プロパティを結びつける重要な機能  
プロパティバインディングは角括弧 [] を使って行われます。これは、コンポーネントのプロパティを HTML 要素のプロパティにバインドするために使用される。  
![Captura desde 2023-12-21 12-29-15](https://github.com/naopeke/Angular-JP/assets/143800388/f36063f8-6e23-4c21-b4ae-df20597b214c)  
ExampleComponent の userName プロパティがテキストボックスの value 属性にバインドされています。このため、テキストボックスには初期値として "John Doe" が表示される。  
    
属性バインディング: DOM の属性にバインドする。例: <div [attr.role]="myRole"></div>  
クラスバインディング: CSS クラスにバインドする。例: <div [class.special]="isSpecial"></div>  
スタイルバインディング: インラインスタイルにバインドする。例: <div [style.color]="isSpecial ? 'red' : 'green'</div>  
## （イベントバインディング）単方向バインディング
ビューからコントローラー  
テンプレート（HTML）内のイベント（ユーザーの操作など）をコンポーネントのメソッドにバインドするためのメカニズム  
（反応させたいDOMイベントの名前）＝”イベントがトリガーされたときに実行されるコンポーネントのメソッド”  
![Captura desde 2023-12-21 12-59-34](https://github.com/naopeke/Angular-JP/assets/143800388/bc63f430-74b2-4e08-9caa-f6da8c8a63d1)  

コンポーネント内でのメソッド定義  
イベントバインディングに関連付けられたメソッドは、コンポーネントのクラス内に定義されます。
![Captura desde 2023-12-21 13-00-26](https://github.com/naopeke/Angular-JP/assets/143800388/07968e03-a3ac-4ad8-b3c3-db298413b77b)  
  
イベントオブジェクトの使用  
イベントハンドラーには、イベントオブジェクトへのアクセスが可能です。  
![Captura desde 2023-12-21 13-11-35](https://github.com/naopeke/Angular-JP/assets/143800388/47b3d1f4-7f03-4574-93eb-4327175c9613)  
$event はクリックイベントのマウスイベントオブジェクトを表します。  

## 双方向バインディング
Two Way Binding
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
