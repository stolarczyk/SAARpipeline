Automatyzacja status/workflow:
- 01_ensembl_peptide_seq_cut.pl (OK. Na wejsciu organizm, wystarczy petla wywolujaca skrypt dla kazdego zadanaego oganizmu)
- 02_run_signalp.pl (OK. Na wejsciu organizm i ilosc plikow wygenerowanych przez 01... W przyszlosci można połączyć z 01...)
- 03_SignalP_positives.pl (OK. Na wejściu organizm, również można połączyć z poprzednimi)
- 04_SigP4_analyzer.pl (OK. Na wejsciu organizm, również można połączyć z poprzednimi)
- shell command: cat sigpL_ALL*/sigp_ALL*>>sigpL_ALL.out/sigp_ALL.out.(OK. Wystarczy dodać do pipelinu)
- 05_Needle_wrappers (OK. Na wejściu organism_and_orthologues_protein_ids.tsv sigpL_ALL.out i organizmy (uwaga, kolejność))
- prep2spl_length_analysis.pl (OK. na wejściu mapper(z powyższego punktu), sigpL-ALL.out i organizmy (uwaga, kolejność))
- SP_LSAAR_length_analysis.R (OK. na wejściu spl_length_analysis_prepped_file_<org>_Ortho.csv i zwraca korelacje. Jakies wykresy dodac ?)
- prep2comp.pl (OK. na weściu output z Needla (ALL_<organizm>_Ortho_all.needle), ortho_dataset.tsv (w zależności od organizmu zainteresowania) i organizmy (uwaga, kolejność)
- SP_compare.R (OK. na wejściu prep2comp_<OoI>_all.csv i OoI(ensembl exclusive code) Ortho(ensembl exclusive code). Zwraca tabelki z AA na miejscu L. Jakies wykresy dodac?)

