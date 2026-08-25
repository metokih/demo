# プロジェクト概要

このプロジェクトは、.NET 10 と ASP.NET Core MVC を使用したWebアプリケーションです。コントローラーとRazorビューによる画面表示を基本構成とし、静的ファイル配信にも対応しています。

## 認証の種類

認証機能は構成されていません。`Program.cs` では認証サービスの登録（`AddAuthentication`）や認証ミドルウェア（`UseAuthentication`）が設定されておらず、ログイン機能やユーザー識別は実装されていません。

認可ミドルウェア（`UseAuthorization`）は配置されていますが、認証方式と認証サービスの設定がないため、現時点で具体的な認証・認可プロバイダーは利用していません。

## 使用されているパッケージ

プロジェクトファイルに明示的なNuGetパッケージ参照（`PackageReference`）はありません。

`Microsoft.NET.Sdk.Web` SDK により、.NET 10 の共有フレームワーク `Microsoft.AspNetCore.App` が暗黙的に参照されます。これに含まれる主な機能は次のとおりです。

- ASP.NET Core MVC（コントローラー、Razorビュー）
- ASP.NET Core Routing
- 静的ファイル配信
- ASP.NET Core の例外処理とHTTPS/HSTS対応

フロントエンド用のライブラリとして、`wwwroot/lib` に Bootstrap、jQuery、jQuery Validation、jQuery Validation Unobtrusive が配置されています。
