# chat_with_pdf

Its a CLI App that use the power of qdrant database and orca framework to answer your question based on the PDF you gave.

## setup

You need to set STANDARD_FONTS to the folder path of where you stored assets/pdf_fonts .
Then downloading "<https://huggingface.co/TheBloke/Mistral-7B-Instruct-v0.1-GGUF/blob/main/mistral-7b-instruct-v0.1.Q4_K_S.gguf>" this model and put it in
models folder.
Then run docker database image.
After that using sample commands to run the app.

## run docker database

```shell
docker pull qdrant/qdrant
docker run -d --name qdrant_test_instance -p 6333:6333 -p 6334:6334 -e QDRANT__SERVICE__GRPC_PORT=6334 qdrant/qdrant
```

## run command

```shell
cargo run --release -- --file ""./game-theory.pdf" --prompt "what is dominant strategy"

cargo run --release -- --file "./naval-book.pdf" --prompt "investing the rest of your life in what has meaning to you"


```
