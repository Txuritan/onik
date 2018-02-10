src = "src/"

dist = "dist/"
file = "onik"

task :watch do |t, args|
	system "sass --watch #{src}:#{dist}"
end

task :compile do |t, args|
	puts "Building #{file}.css..."
	system "sass #{src}#{file}.sass:#{dist}#{file}.css"

	puts "Building #{file}.min.css..."
	system "sass #{src}#{file}.sass:#{dist}#{file}.min.css --style compressed"

	puts "Building #{file}.js..."
	system "coffee -cbmo #{dist} #{src}#{file}.coffee"

	puts "Building index.html..."
	system "haml #{src}index.haml #{dist}index.html"
end

task :serve do |t, args|
	system "ruby -run -e httpd . -p 5000"
end
