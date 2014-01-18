require 'fileutils'

CONTRACTS = %w{ contract kontrakt}

task :default => CONTRACTS

task :open => CONTRACTS do
  CONTRACTS.each do |contract|
  `open build/#{contract}.pdf`
  end
end

task :clean do
  FileUtils.rm_rf "build"
end

CONTRACTS.each do |contract|
  FileUtils.mkdir_p "build"
  task contract do
   `xelatex --output-directory=build -interaction=nonstopmode #{contract}.tex`
  end
end



