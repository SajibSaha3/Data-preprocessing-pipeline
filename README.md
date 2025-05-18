<h1>🧹 Text Preprocessing for Customer Complaints</h1>
<p>
This Python script performs a series of Natural Language Processing (NLP) tasks to clean and standardize informal customer complaints,
particularly for e-commerce-related queries. It includes tasks such as contraction expansion, slang normalization, emoji removal, spell correction, 
 lemmatization, and stopword filtering.
</p>

<h2>📦 Features</h2>
        <li>Decontracts informal language and chat-style shorthand (e.g., <code>u</code> → <code>you</code>, <code>plz</code> → <code>please</code>)</li>
        <li>Handles and removes emojis</li>
        <li>Corrects common spelling mistakes using <code>TextBlob</code></li>
        <li>Tokenizes and lemmatizes text using <code>spaCy</code></li>
        <li>Filters out common English stopwords using <code>nltk</code></li>
    <h2>🧠 Requirements</h2>
    <pre><code>pip install nltk textblob spacy
python -m textblob.download_corpora
python -m spacy download en_core_web_sm</code></pre>
<p>Also, ensure the required NLTK resources are downloaded:</p>
 <pre><code>import nltk
nltk.download('punkt')
nltk.download('stopwords')</code></pre>
 <h2>🧾 Code Overview</h2>
<h3>1. <code>decontracted(phrase)</code></h3>
<p>Expands contractions and normalizes slang/informal abbreviations. Removes inappropriate slangs like <code>af</code>.</p>

<h3>2. <code>remove_emo(text)</code></h3>
<p>Removes emojis from the text using regex.</p>

<h3>3. <code>preprocessing(sentences)</code></h3>
<p>Accepts a list of informal sentences. Applies decontraction, emoji removal, spell correction, tokenization, lemmatization, and returns cleaned sentences.</p>

<h3>4. Final Stopword Removal</h3>
 <p>Tokenizes and filters out stopwords using NLTK’s stopword corpus.</p>
 <h2>🧪 Example</h2>
<p><strong>Input:</strong></p>
 <pre><code>[
  "Hey, can u plz tell me where’s my order??",
  "i didn’t receive my parcel yet!!!!",
  "Whr’s my ordr 😡😡",
  "delivery late af... i want refund now"
]</code></pre>

<p><strong>Output After Preprocessing:</strong></p>
 <pre><code>[
  'Hey can you please tell me where be my order',
  'I do not receive my parcel yet',
  'Where be my order',
  'Delivery late I want a refund now'
]</code></pre>

<p><strong>After Stopword Removal:</strong></p>
<pre><code>[
  'Hey', 'please', 'tell', 'order', 'receive',
  'parcel', 'yet', 'order', 'Delivery', 'late', 'want', 'refund'
]</code></pre>

<h2>🛠️ Future Improvements</h2>

<li>Integrate sentiment analysis to classify complaints</li>
 <li>Add support for multilingual inputs</li>
<li>Include named entity recognition (NER) to identify specific issues</li>
    <h2>📄 License</h2>
    <p>This project is open-source and free to use under the MIT License.</p>
</body>
</html>
