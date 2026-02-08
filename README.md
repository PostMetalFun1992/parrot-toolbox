xargs flatpak install -y flathub < flatpak_list.txt

export UID=$(id -u)
export GID=$(id -g)
docker compose run --rm nmap-user -sV -oN test_report.txt scanme.nmap.org
