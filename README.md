https://kubesphere.io/docs/installing-on-kubernetes/on-prem-kubernetes/install-ks-on-linux-airgapped/

```sh
kubectl apply -f kubesphere-installer.yaml.save
kubectl apply -f cluster-configuration.yaml.save
```

1.20兼容性问题解决
https://kubesphere.com.cn/forum/d/2217-account-is-not-active

```sh
kubectl apply -f https://raw.githubusercontent.com/kubesphere/ks-installer/2c4b479ec65110f7910f913734b3d069409d72a8/roles/ks-core/prepare/files/ks-init/users.iam.kubesphere.io.yaml
kubectl apply -f https://raw.githubusercontent.com/kubesphere/ks-installer/2c4b479ec65110f7910f913734b3d069409d72a8/roles/ks-core/prepare/files/ks-init/webhook-secret.yaml
kubectl -n kubesphere-system rollout restart deploy ks-controller-manager
```

Now, you will be able to access the web console of KubeSphere through `http://{IP}:30880` with the default account and password `admin/P@88w0rd`.
