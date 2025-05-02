data = {"query": ["How to reset password?"], "category": ["Technical Issue"]}
def clean(text): return re.sub(r'[^a-z\s]', '', text.lower())
df['category'].value_counts().plot(kind='bar')
X = TfidfVectorizer().fit_transform(df['clean_query'])
model = MultinomialNB().fit(X_train, y_train)
accuracy_score(y_test, model.predict(X_test))
ConfusionMatrixDisplay.from_estimator(model, X_test, y_test)
print(model.predict(vectorizer.transform([clean(user_input)])))
