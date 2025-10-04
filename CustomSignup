# SwiftUI-Simple-UIs
A collection of simple SwiftUI UIs like buttons, card, and more

import SwiftUI

struct Signup: View {
    
    @State private var email = ""
    @State private var name = ""
    @State private var password = ""
    
    var body: some View {
        ZStack {
            
            Color.yellow.mix(with: .white, by: 0.88).ignoresSafeArea()
            
            VStack(spacing: 40) {
                
                Text("Log in")
                    .font(.title3)
                    .foregroundStyle(.secondary)
                    .frame(maxWidth: .infinity, alignment: .trailing)
                
                VStack(alignment: .leading, spacing: 50) {
                    Text("Sign up")
                        .font(.title.bold())
                    
                    VStack(spacing: 35) {
                        CustomTextField(title: "Your Email", text: $email)
                        CustomTextField(title: "Name", text: $name)
                        CustomTextField(title: "Password", text: $password)
                    }
                }
                
                secondSection

            }
            .padding(.horizontal, 20)
            .padding(.bottom, 20)
        }
    }
    
    @ViewBuilder var firstSection: some View {
        Text("Log in")
            .font(.title3)
            .foregroundStyle(.secondary)
            .frame(maxWidth: .infinity, alignment: .trailing)
        
        VStack(alignment: .leading, spacing: 50) {
            Text("Sign up")
                .font(.title.bold())
            
            VStack(spacing: 35) {
                CustomTextField(title: "Your Email", text: $email)
                CustomTextField(title: "Name", text: $name)
                CustomTextField(title: "Password", text: $password)
            }
        }
    }
    
    @ViewBuilder var secondSection: some View {
        Button {
            
        } label: {
            Text("Sign up")
                .font(.title2.bold())
                .foregroundStyle(.white)
                .frame(width: 350, height: 45)
                .background(
                    RoundedRectangle(cornerRadius: 30)
                        .fill(.black.opacity(0.7))
                )
                .shadow(color: .secondary, radius: 10, y: 10 )
        }
        .padding(.top, 30)
        
        Text("Or sign up with")
            .font(.headline)
            .foregroundStyle(.secondary)
        
        HStack(spacing: 20) {
            button(title: "apple")
            button(title: "google")
        }
        .padding(.vertical)
    }
    
    func button(title: String) -> some View {
        HStack{
            
            Image(title)
                .resizable()
                .renderingMode(.template)
                .foregroundStyle(.secondary)
                .scaledToFit()
                .frame(width: 30)
                
            
            Text("\(title.capitalized) account")
                .font(.headline)
                
        }
        .padding(.vertical, 10)
        .frame(width: 175)
        .background(
            RoundedRectangle(cornerRadius: 30)
                .stroke(.secondary , lineWidth: 2)
        )
    }
}

struct CustomTextField: View {
    
    var title: String
    @Binding var text: String
    @FocusState var isFocused: Bool
    
    var body: some View {
        VStack(alignment: .leading) {
            
            VStack {
                TextField("", text: $text)
                    .font(.title3)
                    .fontWeight(.semibold)
                    .focused($isFocused)
                    .overlay {
                        ZStack {
                            Text(title)
                                .font(isFocused ? .subheadline: text.isEmpty ? .title3 : .subheadline)
                                .foregroundStyle(.secondary)
                                .offset(y: isFocused ? -25 : text.isEmpty ?0 : -25)
                                .frame(maxWidth: .infinity, alignment: .leading)
                                .onTapGesture {
                                    isFocused = true
                                }
                        }
                    }
                
                Rectangle()
                    .frame(height: 2)
                    .foregroundStyle(.secondary)
            }
        }
        .animation(.smooth, value: isFocused)
    }
}

#Preview {
    Signup()
    
}
