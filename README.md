# INDEX
[](#)
1.[インストール](#インストール)  
2.[モジュールの作成](#モジュールの作成)  
3.[コンポーネントの作成](#コンポーネントの作成)  
4.[ダウングレード](#ダウングレード)  
5.[ルーティング](#ルーティング)  
6.[文字列補間（単方向バインディング）](#文字列補間単方向バインディング)  
7.[プロパティバインディング（単方向データバインディング）](#プロパティバインディング単方向データバインディング)  
8.[イベントバインディング（単方向データバインディング）](#イベントバインディング単方向データバインディング)  
8.[双方向データバインディング](#双方向データバインディング)  
9.[ngIf](#ngif)  
10.[ngFor](#ngfor)  
11.[](#)  
12.[](#)  
13.[](#)  
14.[](#)  
15.[](#)  

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

3.＜router-outlet＞の使用: 通常は app.component.html）に <router-outlet> を配置  
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

## プロパティバインディング（単方向データバインディング）
One Way Binding コントローラーからビュー  
コンポーネントのクラスプロパティとテンプレート内の HTML 要素プロパティを結びつける重要な機能  
プロパティバインディングは角括弧 [] を使って行われます。これは、コンポーネントのプロパティを HTML 要素のプロパティにバインドするために使用される。  
![Captura desde 2023-12-21 12-29-15](https://github.com/naopeke/Angular-JP/assets/143800388/f36063f8-6e23-4c21-b4ae-df20597b214c)  
ExampleComponent の userName プロパティがテキストボックスの value 属性にバインドされています。このため、テキストボックスには初期値として "John Doe" が表示される。  
    
属性バインディング: DOM の属性にバインドする。例: <div [attr.role]="myRole"></div>  
クラスバインディング: CSS クラスにバインドする。例: <div [class.special]="isSpecial"></div>  
スタイルバインディング: インラインスタイルにバインドする。例: <div [style.color]="isSpecial ? 'red' : 'green'</div>  
## （イベントバインディング）単方向データバインディング
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

## 双方向データバインディング
Two Way Binding
双方向バインディングでは、以下の二つのプロセスが組み合わさっています：  
プロパティバインディング: コンポーネントのプロパティがテンプレートの属性にバインドされ、コンポーネントの状態がテンプレートに反映されます。  
イベントバインディング: テンプレート内のユーザーのアクション（例えば、テキストボックスへの入力）がコンポーネントのメソッドにバインドされ、それによってコンポーネントの状態が更新されます。  
  
Angular では、[(ngModel)] ディレクティブを使って双方向バインディングを実現します。これは、特にフォーム要素での使用に適しています。  
![Captura desde 2023-12-21 13-39-40](https://github.com/naopeke/Angular-JP/assets/143800388/da0d9f7f-3edb-4e4b-976f-be04f649a783)
この例では、username というコンポーネントのプロパティが <input> 要素の value 属性にバインドされています。ユーザーがテキストボックスに何かを入力すると、username プロパティが自動的に更新されます。同様に、username プロパティの値がプログラム的に変更されると、テキストボックスの表示内容も更新さ
れます。  
![Captura desde 2023-12-21 13-42-05](https://github.com/naopeke/Angular-JP/assets/143800388/46d9844c-57bc-4673-a235-a24cdf4854b4)  
  
![Captura desde 2023-12-21 13-42-40](https://github.com/naopeke/Angular-JP/assets/143800388/90830745-5ed5-4ea2-853a-fdc6b39343b4)  
  
![Captura desde 2023-12-21 13-43-32](https://github.com/naopeke/Angular-JP/assets/143800388/e71270b9-d157-4887-9634-14901eac47de)　　

FormsModule をインポートする　　
FormsModule を @angular/forms パッケージからインポート  
通常、app.module.ts ファイル内で行う。  
![Captura desde 2023-12-21 13-47-39](https://github.com/naopeke/Angular-JP/assets/143800388/e0066bec-b98c-40f6-ac97-a0615735b90c)  

NgModule デコレータの imports 配列に FormsModule を追加  
![Captura desde 2023-12-21 13-48-08](https://github.com/naopeke/Angular-JP/assets/143800388/3058044c-637d-4c04-9280-cb7b4e27fd0e)  

FormsModule は主にテンプレート駆動フォーム（Template-driven Forms）で使用されます。リアクティブフォーム（Reactive Forms）を使用する場合は、代わりに ReactiveFormsModule をインポートする必要があります。  
  
1: ReactiveFormsModule のインポート  
ReactiveFormsModule のインポート:  
通常、アプリケーションのルートモジュール（多くの場合は app.module.ts）で行う。  
![Captura desde 2023-12-21 13-56-45](https://github.com/naopeke/Angular-JP/assets/143800388/05321ae2-cefc-4b36-a41c-894f5bca84dd)  

NgModule デコレータに追加:  
![Captura desde 2023-12-21 13-57-33](https://github.com/naopeke/Angular-JP/assets/143800388/575dec5f-28c6-43d9-8955-cbc6642c75b9)  

2: リアクティブフォームの使用  
![Captura desde 2023-12-21 13-58-40](https://github.com/naopeke/Angular-JP/assets/143800388/87062007-1da5-497a-9227-120c3bdfa7eb)  
テンプレート駆動フォームとリアクティブフォーム、同一アプリケーション内で両方を使用することが可能。ただし、同一のフォーム内で混在させることはできない  。


## ngIf
特定の条件が真（
true）の場合にのみ、DOM上に要素を表示するために使用。条件がfalse の場合、要素はDOMから完全に削除。  
![Captura desde 2023-12-21 14-11-00](https://github.com/naopeke/Angular-JP/assets/143800388/92adf319-e67a-451d-afeb-72a36aeeb1d0)  

*ngIf で使用される条件は、通常、コンポーネントの TypeScript クラス内で定義されたプロパティに基づいています  
![Captura desde 2023-12-21 14-12-14](https://github.com/naopeke/Angular-JP/assets/143800388/0fad1ea6-954d-4bd2-9480-5b4ae61d54b1)  

else 条件を使用して、条件が false の場合に別のテンプレートを表示することもできます。  
![Captura desde 2023-12-21 14-13-10](https://github.com/naopeke/Angular-JP/assets/143800388/eb101762-f56e-401b-af5f-2e8a5087cf9a)
この例では、showMessage が false の場合、「メッセージはありません。」というテキストを含む <p> 要素が表示されます。  
  
## ngFor
*ngFor は *ngFor="let item of items" の形式で使用され、ここで items は配列やオブジェクトのリストを表し、item はリスト内の個々のアイテムを表すローカル変数です。  
![Captura desde 2023-12-21 14-18-10](https://github.com/naopeke/Angular-JP/assets/143800388/03ed06cd-5397-4c8d-9882-94c378288cc8)  

ループ中の各アイテムのインデックスや他の有用な変数にアクセスすることもできる。  
この場合、let i = index で各アイテムのインデックスにアクセスし、1から始まる番号と共にアイテムを表示。
![Captura desde 2023-12-21 14-18-41](https://github.com/naopeke/Angular-JP/assets/143800388/7f6759c9-e6f3-4100-bacc-0d71ac2940a2)　　

大きなリストや複雑なオブジェクトを含むリストを扱う際には、パフォーマンスを最適化するために trackBy 関数を使用することが推奨されます。これにより、Angular はオブジェクトのアイデンティティを追跡し、必要なときのみ DOM を更新します。　　
![Captura desde 2023-12-21 14-20-53](https://github.com/naopeke/Angular-JP/assets/143800388/68a87f23-45ce-4a07-91ee-aa2df20f2e1e)　　

## Pipe

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
