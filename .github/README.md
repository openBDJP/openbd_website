openbd_website [![Deploy](https://github.com/OpenBDJP/openbd_website/actions/workflows/deploy.yml/badge.svg)](https://github.com/OpenBDJP/openbd_website/actions/workflows/deploy.yml)
================
openbd.jpのウェブホスティング

コンセプト
-----
- S3のウェブサイトホスティング
- 複数リージョンにレプリケーション

デプロイ先
-----

https://openbd.jp/

- masterにコミットすると自動的にデプロイされ、キャッシュが無効化されます
- 各バケットの静的ウェブサイトホスティングを有効化（index.html）
- CloudFrontのオリジングループでフェイルオーバーを設定（大阪／サンパウロ）

| リージョンID | 場所 | デプロイ方法 |
|-|-|-|
| [openbd-hosting-ap-northeast-3](https://s3.console.aws.amazon.com/s3/buckets/openbd-hosting-ap-northeast-3?region=ap-northeast-3&tab=objects) | 大阪 | GitHub Actions |
| [openbd-hosting-sa-east-1](https://s3.console.aws.amazon.com/s3/buckets/openbd-hosting-sa-east-1?region=sa-east-1&tab=objects) | サンパウロ | レプリケーション |

- [CloudFront 管理画面](https://console.aws.amazon.com/cloudfront/home?region=ap-northeast-1#distribution-settings:E2CMCI17OO6W7F)
- [デプロイ用のIAMユーザー](https://console.aws.amazon.com/iam/home?region=ap-northeast-1#/users/openbd-hosting-deploy)
- [デプロイツール (s3deploy)](https://github.com/bep/s3deploy)

監視
-----
- [updown.io](https://updown.io/uzx8)


変更履歴
-----
- 2021年4月6日 DeployBotからGitHub Actionsに移行
