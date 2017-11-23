Vagrant.configure('2') do |config|
  config.vm.box      = 'ubuntu/artful64' # 17.10
  config.vm.hostname = 'timesheet-dev-box'

  config.vm.network :forwarded_port, guest: 3000, host: 3000
  config.vm.network :forwarded_port, guest: 3001, host: 3001

  config.vm.provision :shell, path: 'bootstrap.sh', keep_color: true

  config.vm.provider 'virtualbox' do |v|
    v.name   = 'timesheet-dev-box'
    v.memory = ENV.fetch('TIMESHEET_DEV_BOX_RAM', 2048).to_i
    v.cpus   = ENV.fetch('TIMESHEET_DEV_BOX_CPUS', 2).to_i
  end

  config.vm.define 'timesheet-dev-box' do |t|
  end
end