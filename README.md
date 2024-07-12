# WordCloud
import pandas as pd
import matplotlib.pyplot as plt
from wordcloud import WordCloud
from collections import Counter

data = (r"C:\Users\janha\Downloads\Word_cloud.xlsx")
df=pd.read_excel(data)

column_name='Reviews_name'
text_data=' '.join(df[column_name].dropna())

wordcloud= WordCloud(width=800,height=400,background_color='white').generate(text_data)

word=text_data.split()

word_freq=Counter(word)
print(word_freq)

plt.imshow(wordcloud)
plt.axis('off')
plt.show()
