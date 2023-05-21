# ---- Compiler Image ----

FROM ubuntu:20.04 AS compiler

RUN apt-get update 

RUN apt-get install -y --no-install-recommends gcc build-essential

WORKDIR /root

COPY hello.c . 

RUN gcc -o helloworld hello.c

# ---- Runtime Image ----

FROM ubuntu:20.04 AS runtime

COPY --from=compiler /root/helloworld . 

CMD ["./helloworld"]