local rekeste = http and http.request or syn and syn.request or request

hookfunction(rekeste, function(args)
    if args.Url:find("scriptsbinsauth.vercel.app/api/verify%-key") then
        print("hookfunction bem do basic")

        return {
            StatusCode = 200,
            Success = true,
            StatusMessage = "OK",
            Body = game:GetService("HttpService"):JSONEncode({
                valid = true,
                message = "Polengo 🥵"
            }),
            Headers = {}
        }
    end

    return rekeste(args)
end)

print("hookfunction bem do basic")

task.wait(1)

loadstring(game:HttpGet("https://raw.githubusercontent.com/dadad213/sintoniafudido1/refs/heads/main/main"))()
