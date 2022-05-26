load('ext://restart_process', 'docker_build_with_restart')

k8s_yaml('kubernetes.yaml')
k8s_resource('example-nestjs', port_forwards=3000, resource_deps=[])

local_resource(
  'example-ts-compile',
  serve_cmd='npm run build:watch',
)

docker_build_with_restart('example-nestjs-image', '.',
    build_args={'node_env': 'development'},
    entrypoint='node /home/node/dist/main.js',
    live_update=[
        sync('.', '/home/node'),
        run('cd /home/node && npm ci', trigger=['./package.json', './package-lock.json']),
    ],
)
