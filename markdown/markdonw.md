# Pythonを使ってMarkdownからHTMLに変換する方法

#＃ はじめに

プログラミングや技術的な文章を書く際、Markdownはそのシンプルさと柔軟性で非常に人気があります。しかし、ウェブサイトで使用するにはHTML形式が必要です。

Pythonを使用してMarkdownをHTMLに簡単に変換する方法を紹介します。

## 必要なツール

このチュートリアルでは、Pythonの`markdown`ライブラリを使用します。まず、このライブラリをインストールする必要があります。

```bash
    pip install markdown
```

## MarkdownからHTMLへの変換

Pythonスクリプトを作成して、MarkdownファイルをHTMLに変換するプロセスは非常に簡単です。以下のステップに従ってください。

1. **Markdownテキストの準備**:

    まず、変換したいMarkdownテキストを準備します。これはファイルから読み込むことも、直接スクリプト内に書くこともできます。

    ```python
    markdown_text = """
    # 見出し
    これはサンプルテキストです。
    - リスト項目1
    - リスト項目2
    """
    ```

2. **MarkdownをHTMLに変換**:

    次に、`markdown`ライブラリを使用して、MarkdownテキストをHTMLに変換します。

    ```python
    import markdown
    html = markdown.markdown(markdown_text)
    ```

3. **HTMLの出力**:

    変換されたHTMLは、コンソールに出力するか、HTMLファイルに保存することができます。

    ```python
    print(html)
    # または
    with open('output.html', 'w') as file:
        file.write(html)
    ```

    結果は以下のようになります。

    ```console
    <h1>見出し</h1>
    <p>これはサンプルテキストです。</p>
    <ul>
    <li>リスト項目1</li>
    <li>リスト項目2</li>
    </ul>


    ```
    

## 完成したスクリプト

今回、MarkdownからHTMLへの変換を行うスクリプトを作成しました。
このスクリプトは、MarkdownファイルからHTMLファイルを生成します。
また、コードブロックをスタイル付きのHTMLに変換します。



```python
    import markdown
    import sys
    import re
    import html

    def extract_title(markdown_text):
        # 最初の行がタイトルになる
        title_md = markdown_text.split('\n')[0]
        title_html = markdown.markdown(title_md)
        # 最初の１行を削除
        markdown_text = '\n'.join(markdown_text.split('\n')[1:])
        return markdown_text, title_html


```

## まとめ

MarkdownからHTMLへの変換は、Pythonの`markdown`ライブラリを使用すると非常に簡単です。これにより、ブログ投稿、ドキュメント、あるいはその他のウェブコンテンツを効率的に生成することができます。
