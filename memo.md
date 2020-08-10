## 勉強していてわからなかったこと・つまったこと
- Reactのコンポーネントは常にStateを見張っている
  - Stateが変更されたら勝手に再レンダリングされるようになっている
    - なので、変更がある部分はstateに持たせるように設計するとよい
- イベントハンドラ
  - > 「○○イベントが発生したら××の処理に引き渡す」中継役
  - > 「きっかけ（イベント）→気づき（イベントハンドラ）→行動（処理）」の関係
  - onClick,onMouseDownとか
    - http://www.tohoho-web.com/js/onevent.htm
  - onClickであれば、「クリックイベントが発生したらほげほげ」  
  - イベントが発生したらどうすんの？こうするの！を決めてる人

- state
  - > アプリケーションの状態を保持するもので、コンポーネントをどのようにレンダリングするかといった情報を格納する場所
  - stateを設定するには ` setState() `を使用する（引数はstateのオブジェクトを指定する）
    - 今のstate,props -> state更新用オブジェクト
    - setStateは非同期なので記載する際はこんな感じにしてあげたほうがよい
    ```
    this.setState((state, props) => {
      return { count: state.count + 1 };
    });
    ```
  - コンストラクタに書くstateは初期値
     ``` constructor(props) {
    super(props);
    this.state = {
      count: 0
    }; } 
    ```
    - これでcountというstateを保持したことになる(アクセスする際はthis.state.countのようにする)

- 関数を渡す際はthisをつける  

- bind
  - Reactでは他のコンポーネントに渡す関数をbindする必要がある
