### 概要

Apollo の公式チュートリアルを参考に Golang で GraphQL サーバーを立てる

https://www.apollographql.com/blog/graphql/golang/using-graphql-with-golang/

### コマンド

プロジェクトに tools.go を作成する

```
printf '// +build tools\npackage tools\nimport _ "github.com/99designs/gqlgen"' | gofmt > tools.go
go mod tidy
```

初期設定を記述

```
go run github.com/99designs/gqlgen init
```

### 重要点

/graph/schema.graphqls で定義したスキーマを元に gqlgen で生成される。
生成されたクエリやコンテキストやミドルウェアは/graph/generated/generated.go にコード化される
