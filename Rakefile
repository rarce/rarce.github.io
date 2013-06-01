task :pow_setup do
  powder = Dir.home()+"/.pow"
  if File.directory? powder
    begin
      domain = 'blog'
      File.symlink(Dir.pwd, powder+"/"+domain)
    rescue NotImplementedError=>e
      puts "POW setup failed. The " + e.to_s + "."
    end
  else
    puts "It does not appear that POW is installed."
  end 
end