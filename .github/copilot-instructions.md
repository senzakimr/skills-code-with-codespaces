# Copilot 利用ガイドライン

このリポジトリでは GitHub Copilot を活用して効率的に開発を進めることが推奨されています。以下のルールやガイドラインに従ってご利用ください。

## コメント・記述ルール

- **関数やクラスの冒頭には必ず docstring またはコメントを記載してください。**
	- 目的・引数・返り値・例外などを簡潔にまとめること。
- **処理の意図が分かりにくい箇所には、必ずコメントを追加してください。**
- **Copilot の提案をそのまま使う場合も、内容を理解し、必要に応じてコメントを補足してください。**
- **TODO や FIXME コメントは、対応が必要な理由や期限を明記してください。**

### コメント例

```python
def add(a, b):
		"""
		2つの数値を加算して返す
		:param a: int
		:param b: int
		:return: int
		"""
		return a + b  # シンプルな加算処理

## ログ出力ルール

- **ログは可読性・検索性を意識して出力してください。**
- **エラーや例外発生時は、必ずエラーログを出力してください。**
- **ログレベル（INFO, WARNING, ERROR など）を適切に使い分けてください。**
- **個人情報や機密情報はログに出力しないでください。**
- **必要に応じて、処理の開始・終了や重要な分岐点でログを記録してください。**

### ログ出力例（Python）

```python
import logging

logger = logging.getLogger(__name__)

def add(a, b):
	"""
	2つの数値を加算して返す
	:param a: int
	:param b: int
	:return: int
	"""
	logger.info(f"add called: a={a}, b={b}")
	try:
		result = a + b
		logger.info(f"add result: {result}")
		return result
	except Exception as e:
		logger.error(f"add error: {e}")
		raise
```
