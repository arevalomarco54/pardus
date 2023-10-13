FROM alpine:latest

# Update Repository Cache.
RUN apk update

# Install zsh, its powerlevel10k theme, completions and more...
RUN apk add --no-cache zsh zsh-theme-powerlevel10k zsh-completions zsh-syntax-highlighting

# Make zsh the default shell. And make it pretty.
SHELL [ "/bin/zsh", "-c" ]

# Install common programs.
RUN apk add --no-cache coreutils git curl

# Remove old packages.
RUN apk cache clean

# Make plugin directory then link p10k into it.
RUN mkdir -p ~/.local/share/zsh/plugins \
    && ln -s /usr/share/zsh/plugins/* ~/.local/share/zsh/plugins/

# Happy Hacking.
ENTRYPOINT [ "/bin/zsh" , "-i" ]