FROM ahkui/jupyter
LABEL maintainer="ahkui <ahkui@outlook.com>"

ENV JUPYTERHUB_USER_DATA ${JUPYTERHUB_USER_DATA}
ENV JUPYTERHUB_POSTGRES_DB ${JUPYTERHUB_POSTGRES_DB}
ENV JUPYTERHUB_POSTGRES_USER ${JUPYTERHUB_POSTGRES_USER}
ENV JUPYTERHUB_POSTGRES_HOST ${JUPYTERHUB_POSTGRES_HOST}
ENV JUPYTERHUB_POSTGRES_PASSWORD ${JUPYTERHUB_POSTGRES_PASSWORD}
ENV JUPYTERHUB_OAUTH_CALLBACK_URL ${JUPYTERHUB_OAUTH_CALLBACK_URL}
ENV JUPYTERHUB_OAUTH_CLIENT_ID ${JUPYTERHUB_OAUTH_CLIENT_ID}
ENV JUPYTERHUB_OAUTH_CLIENT_SECRET ${JUPYTERHUB_OAUTH_CLIENT_SECRET}
ENV JUPYTERHUB_LOCAL_NOTEBOOK_IMAGE ${JUPYTERHUB_LOCAL_NOTEBOOK_IMAGE}
ENV JUPYTERHUB_ENABLE_NVIDIA ${JUPYTERHUB_ENABLE_NVIDIA}


RUN npm install --no-cache -g \
        configurable-http-proxy \
    && python3 -m pip install --no-cache-dir \
        oauthenticator \
        dockerspawner

COPY jupyterhub_config.py /root/.jupyter/ 
COPY shared_example.json /root/.jupyter/shared.json
COPY admin.txt /root/.jupyter/ 

CMD ["sh", "-c", "jupyterhub upgrade-db && jupyterhub -f /root/.jupyter/jupyterhub_config.py"]

