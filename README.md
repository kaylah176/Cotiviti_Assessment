# Cotiviti_Assessment
Intern Assessment for Cotiviti Position that includes a proof of concept

# Named Entity Recognition (NER) 
The pipeline scans the note for known clinical terms across three entity classes that include diagnoses (mapped to a lexicon), medications, and procedures. It uses a greedy longest-match approach with deduplication, which is how early rule based systes like MetaMap worked. 

# Negation detection 
Before tagging each entity, the pipeline checks a 60 character lookback window for negation cues like "no history of", "denies", or "no evidence of". Negated entities get flagged and struck through. This is the exact problem that tripped up early clinical NP systems and remains a key challenge for LLMs today. 

# ICD-10 mapping with confidence
Confirmed (non-negated) diagnoses are mapped to ICD-10 codes with confidence scores which is the core workflow Cotiviti would use for risk adjustment. The confidence values simulate what a real probabilistic classifier would produce. 

## The code is organized into three clean layers: Data layer, NLP layer, Rendering layer 

# Data layer 
<DIAGNOSES>
