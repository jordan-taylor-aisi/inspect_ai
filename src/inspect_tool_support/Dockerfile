# This Dockerfile creates a Docker image that includes inspect-tool-support code.
# This is the container side code implementation for several inspect tools including
# web_browser, bash_session, and text_editor.

FROM python:3.12-bookworm

# if based on an image without Python
# RUN apt-get update && apt-get install -y python3 python3-pip python3-venv

# Install pipx to manage Python applications in isolated environments and add
# its installation directory to PATH
RUN pip install --root-user-action=ignore pipx
ENV PATH="$PATH:/root/.local/bin"

RUN pipx install inspect-tool-support && \
    inspect-tool-support post-install

# run forever
CMD ["tail", "-f", "/dev/null"]