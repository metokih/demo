# プロジェクト概要

## プロジェクト名
temp（ASP.NET Core MVC アプリケーション）

## 概要
このプロジェクトは、ASP.NET Core 10.0を使用して構築されたMVC（Model-View-Controller）パターンのウェブアプリケーションです。

## 技術スタック
- **フレームワーク**: ASP.NET Core 10.0
- **パターン**: MVC（Model-View-Controller）
- **UI フレームワーク**: Bootstrap、jQuery
- **ビューエンジン**: Razor

## プロジェクト構成

### コアファイル
- **Program.cs**: アプリケーション起動設定、サービス設定、HTTP パイプライン構成
- **temp.csproj**: プロジェクトファイル（Nullable有効、ImplicitUsings有効）

### ディレクトリ構成
- **Controllers/**: アプリケーションロジック
  - HomeController: ホームページ、プライバシーページ、エラーハンドリング
- **Models/**: データモデル
  - ErrorViewModel: エラー情報を保持するモデル
- **Views/**: ユーザーインターフェース
  - Shared/: レイアウトや共有コンポーネント（_Layout.cshtml、_ValidationScriptsPartial.cshtml）
  - Home/: ホーム関連のビュー（Index.cshtml、Privacy.cshtml）
- **Properties/**: プロジェクト設定
  - launchSettings.json: 実行設定
- **wwwroot/**: 静的ファイル
  - css/: スタイルシート（site.css）
  - js/: クライアント側スクリプト（site.js）
  - lib/: 外部ライブラリ（Bootstrap、jQuery、jQuery Validation）

### 設定ファイル
- **appsettings.json**: アプリケーション設定
- **appsettings.Development.json**: 開発環境固有の設定

## 主な機能
1. **ホームページ**: インデックスページの表示
2. **プライバシーページ**: プライバシーポリシーの表示
3. **エラーハンドリング**: 例外処理とエラーページの表示

## 特徴
- HTTPS リダイレクション
- 認可機能を含むセキュリティ設定
- 静的アセットの管理
- Nullable参照型の有効化による型安全性の向上
