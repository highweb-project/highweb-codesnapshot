# highweb-codesnapshot
Code snapshot optimization applied codes based on Chromium 43.0.2357.78

Code snapshot is an optimization which saves compiled code(Baseline-JITed code) of JavaScript source in the storage and loads later when needed.

1. Making snapshot
After building the code, binary named mkcodesnapshot is created.
Snapshot can be created by using this binary with JavaScript file.

2. Using snapshot
Snapshot is loaded from the 'snapshot' folder under the current folder(where chromium is located)
Snapshot is currently distinguished by JavaScript file's name.
Some flags of chromium are needed to use code snapshot now.
--no-sandbox : necessary for current file I/O logic. Will be removed later with modification in file I/O.
--js-flags="--vmo_codeDeser" : set browser mode to use code snapshot.
