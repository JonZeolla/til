# ash
## Command wrapper
`ash` has a nice method to wrap commands using the `ENV` environment variable. Here is a snippet to illustrate:
```bash
image_name="jonzeolla/til/ash/command_wrapper"
docker build -t "${image_name}":latest -<<HEREDOC
FROM alpine:3
RUN echo -e 'cat() {\necho "Before"\ncommand cat "\$@"\necho "After"\n}' > /.function
ENV ENV="/.function"
HEREDOC
docker run -it "${image_name}"
cat /.function
```

