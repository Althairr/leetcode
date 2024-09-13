```python
import pandas as pd

def getDataframeSize(players: pd.DataFrame) -> List[int]:
    df_column, df_row = players.shape
    return [df_column, df_row]
