# Network

## Google Cloud Services
- VPC:Virtual Private Cloud
  - Cloud VPNトンネルまたはCloud Interconnectアタッチメント(VLAN)を経由してトラフィックをルーティングすることにより、オンプレミスからGoogle APIとサービスに接続できる
  - オンプレミスから送信されるGoogle APIとサービストラフィックをprivate.googleapis.comまたはrestricted.googleapis.com という特別なドメインメインのいずれかに関連付けられたIPアドレスに転送する必要がある
- Cloud Load Balancing
  - 容量スケーラーの設定
    - ターゲット容量を変更せずにターゲット容量スケールダウンすることができる。
    - 例：最大使用率が80RPS、容量スケーラが0.5の場合、有効なターゲット容量は40RPSとなる。
- Cloud Router
- Dedicated Interconnect
  - グローバルルーティングをサポート
    - 特定のリージョンへの Interconnect があれば、そこ経由でどのリージョンのサブネットにもアクセスできるようになる
  - LOA-CFA: Letter of Authorization and Connecting Facility Assignment
    - Googleから顧客とNOC（技術担当）にメールで送信ｓれる
    - LOA-CFAをベンダーに送信して、ベンダーが接続をインストールできるようにする必要がある
  - 10 Gbps or 100 Gbps の回線
  - 暗号化されない
- Partner Interconnect
  - 50 Mbps ～ 50 Gbps
  - 暗号化されない
- Cloud IAM
  - Role Launch Stage
    - ALPHA, BETA, GA
    - GUI上では表示されない
- Cloud Armor
  - プレビューモード
    - ルールを適用しなくても、その影響をプレビューできる。プレビューモードでは、Cloud Monitoring にアクションが記録される。

![Cloud Armor](https://raw.githubusercontent.com/a2-ito/notes-google-cloud-certification/master/images/cloudarmor_classes.png)

- Cloud VPC
  - auto mode と custom mode
- 限定公開アクセス
  - 限定公開のGoogleアクセス
  - 外部IPアドレスを持たないVMのサブネットで限定公開のGoogleアクセスを有効にすると、Google APIとサービスで使用される一連の外部IPアドレスにVMを接続できる- enable-os-login
  - os login を有効化または無効化できる
- Shared VPC
  - 組織内の複数プロジェクトのリソースを共通のVPCに接続する
  - BGP設定はホストプロジェクトのみ。
  - Firewall などネットワークポリシの一元管理
  - 接続可能なサービスプロジェクト数が(初期値で)1000
- route-based VPN tunnel
- policy-based VPN tunnel
- Cloud NAT
- Cloud DNS
  - DNSSECを無効にする
    - ドメインのDSレコードすべてを親ゾーンから削除する
      - これによって、リゾルバはDNSSECを使用してドメインデータを検証しなくなる
    - DSレコードがレジストラから削除されたら、DSレコードの削除がすべてのリゾルバに伝搬されるまで待ってから、ゾーンのDNSSECをオフにする必要がある
- VPC flow logs
  - VMインスタンスによって送受信されたネットワークフローのサンプルが記録される
  - ネットワークモニタリング、フォレンジック、リアルタイムセキュリティ分析、費用の最適化に使用できる
- Load Balancer
  - Global
    - Global External HTTP(S) Load Balancing
    - External HTTP(S) Load Balancing (classic)
    - SSL Proxy Load Balancing
    - TCP Proxy Load Balancing
      - PROXYプロトコルを有効にすることで、送信元IPアドレス、宛先IPアドレス、ポート番号を含む追加ヘッダーをインスタンスへリクエストの構成部分として送信する
  - Regional
    - Regional External HTTP(S) Load Balancing
- Circuit Operational Status 
- Direct Peering
  - オンプレ環境とGoogleエッジネットワークの間に直接ピアリング接続が可能
  - Direct Peering は Google Cloud の外部に存在する。Google Workspace アプリケーションにアクセスする必要がない限り、Google Cloud への推奨のアクセス方法は、Dedicated Interconnect または Partner Interconnect となる。
- Career Peering

## Glossary
- ルーティングプロトコル系
  - IGP: Interior Gateway Protocol
    - RIP
      - (v1) クラスフル・ルーティング・プロトコルに該当する古いプロトコル
    - OSPF
      - リンクステートルーティングを使用するドメイン内ルーティングプロトコル
      - AS内で実行される
    - EIGRP
    - IGRP
      - Cisco独自プロトコル
  - EGP: Exterior Gateway Protocol
    - BGP
      - パスベクトルルーティングを使用するドメイン間ルーティングプロトコル
      - AS外で実行される
- Carrer Peering
  - Public IP アドレスレンジが必要。
- Partner Interconnect
  - パートナーの持っているキャパシティに応じて帯域が決まる。
- Dedicated Interconnect
- VPC Flow log
- IKE: Internet Key Exchange
  - IKEv2 を使用すると、トラフィック セレクタごとに複数の CIDR を指定できる
  - v1
  - v2
- TFTP: Trivial File Transfer Protocol
  - UDPを使った軽量なファイル転送プロトコル



