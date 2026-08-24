# プロジェクト概要

## プロジェクト名
temp（ASP.NET Core MVC アプリケーション）

## 概要
このプロジェクトは、ASP.NET Core 10.0を使用して構築されたMVC（Model-View-Controller）パターンのウェブアプリケーションです。

## 認証の種類
このプロジェクトでは**認証機能が明示的に実装されていません**。
- Program.cs に `app.UseAuthorization();` は設定されていますが、`app.UseAuthentication();` ミドルウェアが追加されていない
- ASP.NET Core 10.0 の認証関連パッケージ（Authentication、Authorization、Identity など）は依存関係として利用可能だが、実装されていない状態
- 現在のアプリケーションは**認証なし**で動作

## フレームワークとライブラリ

### バックエンド
- **ASP.NET Core 10.0**: Webアプリケーションフレームワーク
- **MVC パターン**: Model-View-Controller アーキテクチャ
- **Razor**: ASP.NET Core ビューエンジン
- **認証関連パッケージ（未実装）**:
  - Microsoft.AspNetCore.Authentication
  - Microsoft.AspNetCore.Authorization
  - Microsoft.AspNetCore.Identity
  - Microsoft.AspNetCore.Cors

### フロントエンド
- **Bootstrap 5.3.3**: UIフレームワーク（レスポンシブデザイン）
- **jQuery**: JavaScriptライブラリ
- **jQuery Validation**: フォーム検証プラグイン
- **jQuery Validation Unobtrusive**: ASP.NET Core用の非侵襲的な検証統合

## 技術スタック
- **フレームワーク**: ASP.NET Core 10.0
- **パターン**: MVC（Model-View-Controller）
- **UI フレームワーク**: Bootstrap 5.3.3、jQuery
- **ビューエンジン**: Razor
- **プログラミング言語**: C# 12以上（Nullable有効、ImplicitUsings有効）

## プロジェクト構成

### コアファイル
- **Program.cs**: アプリケーション起動設定、サービス設定、HTTP パイプライン構成
  - コントローラーとビューのサービス登録
  - HTTPS リダイレクション設定
  - 例外処理（HSTS、エラーハンドリング）
  - 認可ミドルウェアの設定
- **temp.csproj**: プロジェクトファイル
  - ターゲットフレームワーク: .NET 10.0
  - Nullable参照型: 有効
  - ImplicitUsings: 有効

### ディレクトリ構成
- **Controllers/**: アプリケーションロジック
  - HomeController: ホームページ、プライバシーページ、エラーハンドリング
- **Models/**: データモデル
  - ErrorViewModel: エラー情報を保持するモデル
- **Views/**: ユーザーインターフェース（Razorテンプレート）
  - Shared/: レイアウトや共有コンポーネント
    - _Layout.cshtml: マスターレイアウト
    - _Layout.cshtml.css: レイアウトスタイル
    - _ValidationScriptsPartial.cshtml: 検証スクリプト統合
    - Error.cshtml: エラーページ
  - Home/: ホーム関連のビュー
    - Index.cshtml: ホームページ
    - Privacy.cshtml: プライバシーページ
- **Properties/**: プロジェクト設定
  - launchSettings.json: HTTP/HTTPS 実行設定（ポート 5288/7113）
- **wwwroot/**: 静的ファイル
  - css/: スタイルシート
    - site.css: アプリケーション固有のスタイル
  - js/: クライアント側スクリプト
    - site.js: アプリケーション固有のスクリプト
  - lib/: 外部ライブラリ
    - bootstrap/: Bootstrap 5.3.3
    - jquery/: jQuery
    - jquery-validation/: jQuery Validation
    - jquery-validation-unobtrusive/: jQuery Validation Unobtrusive

### 設定ファイル
- **appsettings.json**: アプリケーション設定（本番環境）
  - ロギング設定（デフォルト: Information、ASP.NET Core: Warning）
  - AllowedHosts: "*"
- **appsettings.Development.json**: 開発環境固有の設定

## 主な機能
1. **ホームページ**: Index.cshtml で ASP.NET Core 学習ドキュメントへのリンクを表示
2. **プライバシーページ**: Privacy.cshtml でプライバシーポリシーを表示
3. **エラーハンドリング**: 例外発生時にエラーページを表示（リクエストIDと詳細情報を記録）

## アプリケーション設定
- **HTTP パイプライン**:
  1. 例外処理（本番環境）
  2. HSTS（HTTP Strict Transport Security）設定
  3. HTTPS リダイレクション
  4. ルーティング
  5. 認可処理
  6. 静的アセット提供

- **デフォルトルーティング**: `{controller=Home}/{action=Index}/{id?}`

## セキュリティ設定
- HTTPS リダイレクション有効
- 認可ミドルウェア設定済み（認証は未実装）
- HSTS（HTTPS Strict Transport Security）設定有効（本番環境）
- 静的アセットのセキュアな管理

## 開発環境
- ターゲットフレームワーク: .NET 10.0
- 開発ポート: HTTP 5288 / HTTPS 7113
- ブラウザ自動起動: 有効
- 言語機能: C# 12以上（Nullable有効、ImplicitUsings有効）
