FROM cmssw/docker-lxr:v0

CMD /bin/rm -rf /lxr/glimpse_db
RUN addgroup --gid 500 lxr
RUN adduser  --uid 500 --gid 500 lxr
COPY index.html /lxr/index.html
COPY cmsbanner.gif /lxr/cmsbanner.gif
COPY custom.d/lxr.conf /lxr/lxr.conf
COPY custom.d/htaccess-index.conf /lxr/custom.d/htaccess-index.conf
COPY custom.d/lxr-2.2.1-baseurl.patch /lxr/custom.d/lxr-2.2.1-baseurl.patch
COPY custom.d/Lang.pm /lxr/lib/LXR/
COPY scripts/entrypoint.sh /entrypoint.sh
copy custom.d/filetype.conf /lxr/templates/filetype.conf
RUN chmod +x /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]

CMD ["/bin/bash"]
