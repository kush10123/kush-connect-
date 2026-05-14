# import { useState } from "react"; import { Heart, MessageCircle, ShieldCheck, Crown, Users } from "lucide-react";

export default function KushConnectWebsite() { const [loggedIn, setLoggedIn] = useState(false); const [adminView, setAdminView] = useState(false);

const profiles = [ { name: "Sophia", age: 24, bio: "Loves nightlife and exciting conversations.", image: "https://picsum.photos/400/500?1", }, { name: "Luna", age: 22, bio: "Travel addict and fun personality.", image: "https://picsum.photos/400/500?2", }, { name: "Mia", age: 26, bio: "Private vibes and premium energy.", image: "https://picsum.photos/400/500?3", }, ];

return ( <div className="min-h-screen bg-black text-white font-sans"> {!loggedIn && ( <div className="fixed inset-0 z-50 flex items-center justify-center bg-black/90 p-4"> <div className="w-full max-w-md rounded-3xl border border-pink-500/20 bg-zinc-900 p-8 shadow-2xl"> <h1 className="mb-6 text-center text-4xl font-bold text-pink-500"> Kush Connect </h1>

<p className="mb-6 text-center text-gray-400">
          Login or create your account.
        </p>

        <input
          type="email"
          placeholder="Email"
          className="mb-4 w-full rounded-2xl border border-zinc-700 bg-black p-4"
        />

        <input
          type="password"
          placeholder="Password"
          className="mb-6 w-full rounded-2xl border border-zinc-700 bg-black p-4"
        />

        <button
          onClick={() => setLoggedIn(true)}
          className="w-full rounded-2xl bg-pink-600 py-4 text-lg font-bold hover:bg-pink-700"
        >
          Continue
        </button>
      </div>
    </div>
  )}

  <header className="sticky top-0 z-40 flex items-center justify-between border-b border-pink-500/20 bg-black/80 p-6 backdrop-blur">
    <div>
      <h1 className="text-3xl font-bold text-pink-500">
        Kush Connect
      </h1>
    </div>

    <nav className="flex items-center gap-6 text-sm text-gray-300">
      <a href="#home" className="hover:text-pink-400">
        Home
      </a>
      <a href="#profiles" className="hover:text-pink-400">
        Profiles
      </a>
      <a href="#chat" className="hover:text-pink-400">
        Chat
      </a>
      <a href="#premium" className="hover:text-pink-400">
        Premium
      </a>

      <button
        onClick={() => setAdminView(!adminView)}
        className="rounded-xl bg-pink-600 px-4 py-2 hover:bg-pink-700"
      >
        {adminView ? "User View" : "Admin Panel"}
      </button>
    </nav>
  </header>

  <section
    id="home"
    className="bg-gradient-to-b from-pink-900/20 to-black px-6 py-24 text-center"
  >
    <h2 className="mb-6 text-6xl font-bold leading-tight">
      Meet Verified Women Near You
    </h2>

    <p className="mx-auto mb-10 max-w-2xl text-lg text-gray-400">
      Private messaging, premium memberships, secure chatting and real-time connections.
    </p>

    <div className="flex flex-wrap justify-center gap-4">
      <button className="rounded-2xl bg-pink-600 px-8 py-4 text-lg font-bold hover:bg-pink-700">
        Start Matching
      </button>

      <button className="rounded-2xl border border-pink-500 px-8 py-4 text-lg hover:bg-pink-500/10">
        Explore Profiles
      </button>
    </div>
  </section>

  <section className="mx-auto grid max-w-7xl gap-6 px-6 py-16 md:grid-cols-4">
    {[
      {
        title: "Verified Profiles",
        icon: <ShieldCheck className="h-10 w-10 text-pink-500" />,
      },
      {
        title: "Live Messaging",
        icon: <MessageCircle className="h-10 w-10 text-pink-500" />,
      },
      {
        title: "Premium Access",
        icon: <Crown className="h-10 w-10 text-pink-500" />,
      },
      {
        title: "Large Community",
        icon: <Users className="h-10 w-10 text-pink-500" />,
      },
    ].map((feature, index) => (
      <div
        key={index}
        className="rounded-3xl border border-pink-500/20 bg-zinc-900 p-6 text-center"
      >
        <div className="mb-4 flex justify-center">{feature.icon}</div>
        <h3 className="mb-2 text-xl font-bold text-pink-400">
          {feature.title}
        </h3>
        <p className="text-sm text-gray-400">
          Modern platform with premium features and secure access.
        </p>
      </div>
    ))}
  </section>

  <section id="profiles" className="px-6 py-16">
    <h2 className="mb-12 text-center text-5xl font-bold text-pink-500">
      Featured Profiles
    </h2>

    <div className="mx-auto grid max-w-7xl gap-8 md:grid-cols-3">
      {profiles.map((profile, index) => (
        <div
          key={index}
          className="overflow-hidden rounded-3xl border border-pink-500/20 bg-zinc-900 shadow-2xl"
        >
          <img
            src={profile.image}
            alt={profile.name}
            className="h-96 w-full object-cover"
          />

          <div className="p-6">
            <div className="mb-3 flex items-center justify-between">
              <h3 className="text-3xl font-bold">{profile.name}</h3>
              <span className="text-pink-400">{profile.age}</span>
            </div>

            <p className="mb-6 text-gray-400">{profile.bio}</p>

            <button className="flex w-full items-center justify-center gap-2 rounded-2xl bg-pink-600 py-4 font-bold hover:bg-pink-700">
              <Heart className="h-5 w-5" />
              Match Now
            </button>
          </div>
        </div>
      ))}
    </div>
  </section>

  <section
    id="chat"
    className="border-y border-pink-500/20 bg-zinc-950 px-6 py-20"
  >
    <div className="mx-auto max-w-5xl rounded-3xl border border-pink-500/20 bg-zinc-900 p-8">
      <h2 className="mb-10 text-center text-5xl font-bold text-pink-500">
        Live Chat
      </h2>

      <div className="mb-6 space-y-4">
        <div className="w-fit max-w-sm rounded-2xl bg-black p-4">
          Hey ❤️
        </div>

        <div className="ml-auto w-fit max-w-sm rounded-2xl bg-pink-600 p-4">
          Wanna hang out tonight?
        </div>
      </div>

      <div className="flex gap-4">
        <input
          type="text"
          placeholder="Type a message..."
          className="flex-1 rounded-2xl border border-zinc-700 bg-black p-4"
        />

        <button className="rounded-2xl bg-pink-600 px-8 font-bold hover:bg-pink-700">
          Send
        </button>
      </div>
    </div>
  </section>

  <section id="premium" className="px-6 py-20">
    <h2 className="mb-12 text-center text-5xl font-bold text-pink-500">
      Premium Plans
    </h2>

    <div className="mx-auto grid max-w-5xl gap-8 md:grid-cols-2">
      <div className="rounded-3xl border border-zinc-700 bg-zinc-900 p-8">
        <h3 className="mb-4 text-3xl font-bold">Free</h3>
        <p className="mb-6 text-5xl font-bold text-pink-400">$0</p>

        <ul className="space-y-3 text-gray-400">
          <li>Basic matching</li>
          <li>Limited messaging</li>
          <li>Public profiles</li>
        </ul>
      </div>

      <div className="rounded-3xl border border-pink-500 bg-zinc-900 p-8 shadow-2xl shadow-pink-500/20">
        <h3 className="mb-4 text-3xl font-bold">Premium</h3>
        <p className="mb-6 text-5xl font-bold text-pink-400">$19</p>

        <ul className="space-y-3 text-gray-400">
          <li>Unlimited messaging</li>
          <li>Verified badge</li>
          <li>Priority matching</li>
          <li>Private galleries</li>
        </ul>
      </div>
    </div>
  </section>

  {adminView && (
    <section className="border-t border-pink-500/20 bg-zinc-950 px-6 py-20">
      <div className="mx-auto max-w-7xl">
        <h2 className="mb-12 text-center text-5xl font-bold text-pink-500">
          Admin Dashboard
        </h2>

        <div className="mb-10 grid gap-6 md:grid-cols-3">
          <div className="rounded-3xl border border-pink-500/20 bg-zinc-900 p-8">
            <h3 className="mb-3 text-xl font-bold">Total Users</h3>
            <p className="text-5xl font-bold text-pink-400">1,240</p>
          </div>

          <div className="rounded-3xl border border-pink-500/20 bg-zinc-900 p-8">
            <h3 className="mb-3 text-xl font-bold">Messages</h3>
            <p className="text-5xl font-bold text-pink-400">8,502</p>
          </div>

          <div className="rounded-3xl border border-pink-500/20 bg-zinc-900 p-8">
            <h3 className="mb-3 text-xl font-bold">Reports</h3>
            <p className="text-5xl font-bold text-pink-400">18</p>
          </div>
        </div>

        <div className="overflow-auto rounded-3xl border border-pink-500/20 bg-zinc-900 p-6">
          <table className="w-full text-left">
            <thead>
              <tr className="border-b border-zinc-700 text-pink-400">
                <th className="py-4">Username</th>
                <th>Status</th>
                <th>Membership</th>
                <th>Action</th>
              </tr>
            </thead>

            <tbody>
              <tr className="border-b border-zinc-800">
                <td className="py-4">Sophia24</td>
                <td>Active</td>
                <td>Premium</td>
                <td>
                  <button className="rounded-xl bg-pink-600 px-4 py-2 hover:bg-pink-700">
                    Manage
                  </button>
                </td>
              </tr>

              <tr className="border-b border-zinc-800">
                <td className="py-4">LunaX</td>
                <td>Pending</td>
                <td>Free</td>
                <td>
                  <button className="rounded-xl bg-pink-600 px-4 py-2 hover:bg-pink-700">
                    Manage
                  </button>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </section>
  )}

  <footer className="border-t border-pink-500/20 py-8 text-center text-gray-400">
    © 2026 Kush Connect. All rights reserved.
  </footer>
</div>

); }
