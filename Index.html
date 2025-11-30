<!DOCTYPE html>

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ServiceCall AI Dashboard</title>
    <script crossorigin src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body { margin: 0; font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', sans-serif; }
    </style>
</head>
<body>
    <div id="root"></div>
    <script type="text/babel">
        const { useState, useEffect } = React;

```
    const storage = {
        async get(key) {
            try {
                const value = localStorage.getItem(key);
                return value ? { value } : null;
            } catch (e) { return null; }
        },
        async set(key, value) {
            try {
                localStorage.setItem(key, value);
                return { key, value };
            } catch (e) { return null; }
        }
    };

    const CallBotDashboard = () => {
        const [currentUser, setCurrentUser] = useState(null);
        const [loginEmail, setLoginEmail] = useState('');
        const [loginPassword, setLoginPassword] = useState('');
        const [showPassword, setShowPassword] = useState(false);
        const [activeTab, setActiveTab] = useState('dashboard');
        const [calls, setCalls] = useState([]);
        const [users, setUsers] = useState([]);
        const [selectedCall, setSelectedCall] = useState(null);
        const [loading, setLoading] = useState(false);
        const [error, setError] = useState(null);
        const [settings, setSettings] = useState({
            businessPhone: '', blandPhoneNumber: '', aiMode: 'afterhours',
            businessHoursStart: '09:00', businessHoursEnd: '17:00', maxRings: '3', enabled: false
        });

        const BLAND_API_KEY = 'sk-j6w8t75w7jsczvjxvf0x1xsgjn2yqvh05zqiiq8rw7kk78e8s55m8tvvlxd0ypnlye';

        useEffect(() => { initializeData(); }, []);

        const initializeData = async () => {
            const defaultUsers = [
                { id: '1', email: 'admin@servicecall.com', password: 'admin123', role: 'admin', name: 'Admin User', businessName: 'ServiceCall AI' },
                { id: '2', email: 'demo@hvac.com', password: 'demo123', role: 'user', name: 'Quick Fix HVAC', businessName: 'Quick Fix HVAC' }
            ];
            const usersResult = await storage.get('users');
            if (usersResult?.value) {
                setUsers(JSON.parse(usersResult.value));
            } else {
                setUsers(defaultUsers);
                await storage.set('users', JSON.stringify(defaultUsers));
            }
            const callsResult = await storage.get('calls');
            if (callsResult?.value) setCalls(JSON.parse(callsResult.value));
        };

        const handleLogin = () => {
            const user = users.find(u => u.email === loginEmail && u.password === loginPassword);
            if (user) {
                setCurrentUser(user);
                setLoginEmail('');
                setLoginPassword('');
                setError(null);
                loadUserSettings(user.id);
            } else {
                setError('Invalid credentials');
            }
        };

        const loadUserSettings = async (userId) => {
            const settingsResult = await storage.get(`settings_${userId}`);
            if (settingsResult?.value) setSettings(JSON.parse(settingsResult.value));
        };

        const saveSettings = async () => {
            await storage.set(`settings_${currentUser.id}`, JSON.stringify(settings));
            alert('Settings saved!');
        };

        const handleLogout = () => {
            setCurrentUser(null);
            setActiveTab('dashboard');
            setSelectedCall(null);
        };

        const addSampleCall = async () => {
            const sampleCall = {
                id: `sample_${Date.now()}`, userId: currentUser.id, businessName: currentUser.businessName,
                callerName: 'Sarah Johnson', callerPhone: '(555) 987-6543', timestamp: new Date().toISOString(),
                duration: '3:45', serviceScheduled: true, serviceDate: '2024-12-05T10:00:00',
                serviceType: 'Emergency', summary: 'Emergency heating repair. Service scheduled for tomorrow at 10 AM.',
                transcript: 'AI: Thank you for calling. How can I help?\nCaller: My heating stopped working.\nAI: I can schedule emergency service for tomorrow at 10 AM.\nCaller: Perfect, thank you!',
                status: 'completed'
            };
            const updatedCalls = [...calls, sampleCall];
            setCalls(updatedCalls);
            await storage.set('calls', JSON.stringify(updatedCalls));
        };

        const userCalls = currentUser?.role === 'admin' ? calls : calls.filter(c => c.userId === currentUser?.id);
        const totalCalls = userCalls.length;
        const scheduledServices = userCalls.filter(c => c.serviceScheduled).length;
        const emergencyCalls = userCalls.filter(c => c.serviceType === 'Emergency').length;

        if (!currentUser) {
            return (
                <div className="min-h-screen bg-gray-900 flex items-center justify-center p-4">
                    <div className="bg-gray-800 rounded-lg shadow-2xl p-8 w-full max-w-md border border-gray-700">
                        <div className="text-center mb-8">
                            <h1 className="text-3xl font-bold text-white mb-2">ServiceCall AI</h1>
                            <p className="text-gray-400">HVAC • Plumbing • Electrical</p>
                        </div>
                        {error && (
                            <div className="mb-4 p-3 bg-red-900/50 border border-red-700 rounded-lg">
                                <p className="text-sm text-red-300">{error}</p>
                            </div>
                        )}
                        <div className="space-y-4">
                            <div>
                                <label className="block text-sm font-medium text-gray-300 mb-1">Email</label>
                                <input type="email" value={loginEmail} onChange={(e) => setLoginEmail(e.target.value)}
                                    onKeyPress={(e) => e.key === 'Enter' && handleLogin()}
                                    className="w-full px-4 py-2 bg-gray-700 border border-gray-600 rounded-lg text-white" placeholder="Enter email" />
                            </div>
                            <div>
                                <label className="block text-sm font-medium text-gray-300 mb-1">Password</label>
                                <input type={showPassword ? "text" : "password"} value={loginPassword}
                                    onChange={(e) => setLoginPassword(e.target.value)} onKeyPress={(e) => e.key === 'Enter' && handleLogin()}
                                    className="w-full px-4 py-2 bg-gray-700 border border-gray-600 rounded-lg text-white" placeholder="Enter password" />
                            </div>
                            <button onClick={handleLogin} className="w-full bg-blue-600 text-white py-2 rounded-lg hover:bg-blue-700 font-medium">
                                Sign In
                            </button>
                        </div>
                        <div className="mt-6 p-4 bg-gray-700/50 rounded-lg">
                            <p className="text-sm font-medium text-gray-300 mb-2">Demo:</p>
                            <p className="text-xs text-gray-400">admin@servicecall.com / admin123</p>
                            <p className="text-xs text-gray-400">demo@hvac.com / demo123</p>
                        </div>
                    </div>
                </div>
            );
        }

        return (
            <div className="min-h-screen bg-gray-900 text-gray-100">
                <header className="bg-gray-800 shadow-lg border-b border-gray-700">
                    <div className="max-w-7xl mx-auto px-4 py-4 flex items-center justify-between">
                        <div>
                            <h1 className="text-2xl font-bold text-white">ServiceCall AI</h1>
                            <p className="text-sm text-gray-400">{currentUser.businessName}</p>
                        </div>
                        <button onClick={handleLogout} className="px-4 py-2 bg-red-600 text-white rounded-lg hover:bg-red-700">
                            Logout
                        </button>
                    </div>
                </header>

                <nav className="bg-gray-800 border-b border-gray-700">
                    <div className="max-w-7xl mx-auto px-4">
                        <div className="flex space-x-8">
                            {['dashboard', 'calls', 'settings'].map(tab => (
                                <button key={tab} onClick={() => { setActiveTab(tab); setSelectedCall(null); }}
                                    className={`py-4 px-2 border-b-2 font-medium text-sm capitalize ${
                                        activeTab === tab ? 'border-blue-500 text-blue-500' : 'border-transparent text-gray-400'}`}>
                                    {tab}
                                </button>
                            ))}
                        </div>
                    </div>
                </nav>

                <main className="max-w-7xl mx-auto px-4 py-8">
                    {activeTab === 'dashboard' && (
                        <div className="space-y-6">
                            <div className="grid grid-cols-1 md:grid-cols-4 gap-6">
                                <div className="bg-gray-800 p-6 rounded-lg border border-gray-700">
                                    <p className="text-sm text-gray-400">Total Calls</p>
                                    <p className="text-3xl font-bold text-white mt-2">{totalCalls}</p>
                                </div>
                                <div className="bg-gray-800 p-6 rounded-lg border border-gray-700">
                                    <p className="text-sm text-gray-400">Services Booked</p>
                                    <p className="text-3xl font-bold text-green-500 mt-2">{scheduledServices}</p>
                                </div>
                                <div className="bg-gray-800 p-6 rounded-lg border border-gray-700">
                                    <p className="text-sm text-gray-400">Emergency</p>
                                    <p className="text-3xl font-bold text-orange-500 mt-2">{emergencyCalls}</p>
                                </div>
                                <div className="bg-gray-800 p-6 rounded-lg border border-gray-700">
                                    <p className="text-sm text-gray-400">Rate</p>
                                    <p className="text-3xl font-bold text-purple-500 mt-2">
                                        {totalCalls > 0 ? ((scheduledServices / totalCalls) * 100).toFixed(0) : 0}%
                                    </p>
                                </div>
                            </div>

                            {userCalls.length === 0 ? (
                                <div className="bg-gray-800 border border-gray-700 rounded-lg p-12 text-center">
                                    <h3 className="text-lg font-semibold text-white mb-4">No calls yet</h3>
                                    <button onClick={addSampleCall} className="px-6 py-2 bg-blue-600 text-white rounded-lg hover:bg-blue-700">
                                        Add Sample Call
                                    </button>
                                </div>
                            ) : (
                                <div className="bg-gray-800 rounded-lg border border-gray-700">
                                    <div className="p-6 border-b border-gray-700 flex justify-between">
                                        <h2 className="text-xl font-bold text-white">Recent Calls</h2>
                                        <button onClick={addSampleCall} className="px-4 py-2 bg-gray-700 rounded-lg hover:bg-gray-600 text-white text-sm">
                                            + Sample
                                        </button>
                                    </div>
                                    <div className="divide-y divide-gray-700">
                                        {userCalls.slice(-5).reverse().map((call) => (
                                            <div key={call.id} className="p-6 hover:bg-gray-750 cursor-pointer" 
                                                onClick={() => { setSelectedCall(call); setActiveTab('calls'); }}>
                                                <div className="flex justify-between">
                                                    <div className="flex-1">
                                                        <h3 className="text-lg font-semibold text-white mb-2">{call.callerName}</h3>
                                                        <p className="text-sm text-gray-400 mb-1">{call.callerPhone}</p>
                                                        <p className="text-sm text-gray-300">{call.summary}</p>
                                                    </div>
                                                    <div className="text-right ml-4">
                                                        <p className="text-sm text-gray-400">{new Date(call.timestamp).toLocaleDateString()}</p>
                                                        <p className="text-sm font-medium text-white mt-1">{call.duration}</p>
                                                    </div>
                                                </div>
                                            </div>
                                        ))}
                                    </div>
                                </div>
                            )}
                        </div>
                    )}

                    {activeTab === 'calls' && !selectedCall && (
                        <div className="bg-gray-800 rounded-lg border border-gray-700">
                            <div className="p-6 border-b border-gray-700">
                                <h2 className="text-xl font-bold text-white">All Calls</h2>
                            </div>
                            <div className="divide-y divide-gray-700">
                                {userCalls.length === 0 ? (
                                    <div className="p-12 text-center text-gray-400">No calls yet</div>
                                ) : (
                                    [...userCalls].reverse().map((call) => (
                                        <div key={call.id} className="p-6 hover:bg-gray-750 cursor-pointer" onClick={() => setSelectedCall(call)}>
                                            <div className="flex justify-between">
                                                <div className="flex-1">
                                                    <h3 className="text-lg font-semibold text-white mb-1">{call.callerName}</h3>
                                                    <p className="text-sm text-gray-400">{call.callerPhone}</p>
                                                    <p className="text-sm text-gray-300 mt-2">{call.summary}</p>
                                                </div>
                                                <div className="text-right">
                                                    <p className="text-sm text-gray-400">{new Date(call.timestamp).toLocaleDateString()}</p>
                                                    <p className="text-sm font-medium mt-1">{call.duration}</p>
                                                </div>
                                            </div>
                                        </div>
                                    ))
                                )}
                            </div>
                        </div>
                    )}

                    {activeTab === 'calls' && selectedCall && (
                        <div className="space-y-6">
                            <button onClick={() => setSelectedCall(null)} className="text-blue-400 hover:text-blue-300">← Back</button>
                            <div className="bg-gray-800 rounded-lg border border-gray-700">
                                <div className="bg-gradient-to-r from-blue-600 to-blue-800 p-6 text-white">
                                    <h2 className="text-2xl font-bold">{selectedCall.callerName}</h2>
                                    <p className="text-blue-100">{selectedCall.callerPhone}</p>
                                </div>
                                <div className="p-6">
                                    <h3 className="text-lg font-semibold text-white mb-2">Summary</h3>
                                    <p className="text-gray-300 mb-4">{selectedCall.summary}</p>
                                    <h3 className="text-lg font-semibold text-white mb-2">Transcript</h3>
                                    <div className="bg-gray-900 rounded-lg p-4 text-sm text-gray-300 whitespace-pre-wrap max-h-96 overflow-y-auto">
                                        {selectedCall.transcript}
                                    </div>
                                </div>
                            </div>
                        </div>
                    )}

                    {activeTab === 'settings' && (
                        <div className="bg-gray-800 rounded-lg border border-gray-700 p-6">
                            <h2 className="text-2xl font-bold text-white mb-6">Call Forwarding Settings</h2>
                            <div className="space-y-6">
                                <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
                                    <div>
                                        <label className="block text-sm font-medium text-gray-300 mb-2">Business Phone</label>
                                        <input type="tel" value={settings.businessPhone}
                                            onChange={(e) => setSettings({...settings, businessPhone: e.target.value})}
                                            placeholder="(555) 123-4567"
                                            className="w-full px-4 py-2 bg-gray-700 border border-gray-600 rounded-lg text-white" />
                                    </div>
                                    <div>
                                        <label className="block text-sm font-medium text-gray-300 mb-2">Bland AI Number</label>
                                        <input type="tel" value={settings.blandPhoneNumber}
                                            onChange={(e) => setSettings({...settings, blandPhoneNumber: e.target.value})}
                                            placeholder="(555) 987-6543"
                                            className="w-full px-4 py-2 bg-gray-700 border border-gray-600 rounded-lg text-white" />
                                    </div>
                                </div>

                                <div>
                                    <label className="block text-sm font-medium text-gray-300 mb-3">AI Answer Mode</label>
                                    <div className="space-y-3">
                                        <label className="flex items-start space-x-3 p-4 bg-gray-700 rounded-lg cursor-pointer">
                                            <input type="radio" name="aiMode" value="afterhours" checked={settings.aiMode === 'afterhours'}
                                                onChange={(e) => setSettings({...settings, aiMode: e.target.value})} />
                                            <div>
                                                <span className="font-semibold text-white">After Hours Only</span>
                                                <p className="text-sm text-gray-300">AI answers when business is closed</p>
                                            </div>
                                        </label>
                                        <label className="flex items-start space-x-3 p-4 bg-gray-700 rounded-lg cursor-pointer">
                                            <input type="radio" name="aiMode" value="overflow" checked={settings.aiMode === 'overflow'}
                                                onChange={(e) => setSettings({...settings, aiMode: e.target.value})} />
                                            <div>
                                                <span className="font-semibold text-white">Overflow</span>
                                                <p className="text-sm text-gray-300">AI answers when staff is busy</p>
                                            </div>
                                        </label>
                                    </div>
                                </div>

                                {settings.aiMode === 'afterhours' && (
                                    <div className="grid grid-cols-2 gap-4">
                                        <div>
                                            <label className="block text-sm text-gray-300 mb-2">Start Time</label>
                                            <input type="time" value={settings.businessHoursStart}
                                                onChange={(e) => setSettings({...settings, businessHoursStart: e.target.value})}
                                                className="w-full px-4 py-2 bg-gray-700 border border-gray-600 rounded-lg text-white" />
                                        </div>
                                        <div>
                                            <label className="block text-sm text-gray-300 mb-2">End Time</label>
                                            <input type="time" value={settings.businessHoursEnd}
                                                onChange={(e) => setSettings({...settings, businessHoursEnd: e.target.value})}
                                                className="w-full px-4 py-2 bg-gray-700 border border-gray-600 rounded-lg text-white" />
                                        </div>
                                    </div>
                                )}

                                {settings.aiMode === 'overflow' && (
                                    <div>
                                        <label className="block text-sm text-gray-300 mb-2">Rings Before AI</label>
                                        <select value={settings.maxRings} onChange={(e) => setSettings({...settings, maxRings: e.target.value})}
                                            className="w-full px-4 py-2 bg-gray-700 border border-gray-600 rounded-lg text-white">
                                            <option value="2">2 rings</option>
                                            <option value="3">3 rings</option>
                                            <option value="4">4 rings</option>
                                            <option value="5">5 rings</option>
                                        </select>
                                    </div>
                                )}

                                <button onClick={saveSettings} className="w-full px-6 py-2 bg-blue-600 text-white rounded-lg hover:bg-blue-700 font-medium">
                                    Save Settings
                                </button>
                            </div>
                        </div>
                    )}
                </main>
            </div>
        );
    };

    ReactDOM.render(<CallBotDashboard />, document.getElementById('root'));
</script>
```

</body>
</html>
