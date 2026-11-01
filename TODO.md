# TODO

## Drop the stated cause for farm-wide water stress

The teacher rule in `03_teacher` (`RULES`) says: "For the whole farm, the heat is the cause, so suggest longer or more frequent irrigation." The triage record does not report heat, and other rules forbid naming a cause the record does not report. The fine-tuned 0.8B writes "The heat is the cause." in 12 of the 18 test records with a farm-wide water-stress item where water still reaches the soil. Haiku wrote it in 5 of the 14 training messages for that case.

Fix, at the next retraining:

1. Change the rule to "For the whole farm, suggest longer or more frequent irrigation."
2. Relabel the training and validation records with Haiku under the new prompt version.
3. Retrain and score the 0.8B on 199 examples (and the other runs, if the learning curve should use the new prompt).
4. Re-export the GGUF files, score them, and update the checksum in the "Running on the UNO Q" section of `07_export`.
